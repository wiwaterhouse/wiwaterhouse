# Set Orphaned Teaching Slides to Inactive

**Purpose:** Mark all orphaned teaching slides as `IsActive = False` in Rock RMS  
**Target:** Files in the `orphaned_files` table that currently have `IsActive = True`  
**Date:** December 4, 2025

---

## ⚠️ Pre-Requisites

- The `orphaned_files` table must be populated (from the orphaned files query)
- You have write access to the `AttributeValue` table
- Recommended: Test in Dev environment first

---

## 📋 SQL Query (Transaction-Wrapped)

```SQL
-- ==============================================================================
-- Set IsActive = False for orphaned teaching slides (SIMPLIFIED)
-- ==============================================================================

BEGIN TRANSACTION;

-- Preview: See what will be updated
SELECT 
    o.BinaryFileId,
    o.FileName,
    o.ContentTitle,
    o.IsActive AS CurrentStatus,
    o.ModifiedByPerson AS UploadedBy,
    o.ModifiedDate,
    o.RockUrl
FROM orphaned_files o
WHERE o.IsActive = 'True'
ORDER BY o.ModifiedDate DESC;

-- Perform the update (PRESERVES original ModifiedBy and ModifiedDateTime)
UPDATE av
SET av.Value = 'False'
FROM AttributeValue av
INNER JOIN AttributeValue av_file ON av_file.EntityId = av.EntityId
INNER JOIN orphaned_files o ON av_file.Value = CAST(o.BinaryFileGuid AS NVARCHAR(36))
WHERE av.AttributeId = 4701  -- IsActive attribute
  AND av.Value = 'True'      -- Only currently active ones
  AND o.IsActive = 'True';   -- Match with orphaned_files

-- Show how many were updated
SELECT @@ROWCOUNT AS RowsUpdated;

-- Verify: Check that they're now False
SELECT 
    o.BinaryFileId,
    o.FileName,
    av.Value AS NewIsActiveValue,
    av.ModifiedDateTime AS JustUpdated
FROM orphaned_files o
INNER JOIN AttributeValue av_file ON av_file.Value = CAST(o.BinaryFileGuid AS NVARCHAR(36))
INNER JOIN AttributeValue av ON av.EntityId = av_file.EntityId
WHERE av.AttributeId = 4701
  AND o.IsActive = 'True'  -- Originally active
ORDER BY av.ModifiedDateTime DESC;

-- ⚠️ REVIEW THE RESULTS, THEN CHOOSE ONE:

-- Option 1: Everything looks good? Make it permanent:
-- COMMIT TRANSACTION;

-- Option 2: Something wrong? Undo everything:
-- ROLLBACK TRANSACTION;
```

---

## 🔍 How to Use

### Step 1: Run the Query Block
Copy and paste the entire query block into SQL Server Management Studio (SSMS) and execute it.

### Step 2: Review the Results
The query will show you:
1. **Preview results** - Which files will be affected
2. **Row count** - How many `AttributeValue` records were updated
3. **Verification** - The new values (should show `'False'`)

### Step 3: Make Your Decision
After reviewing the results, **execute ONE of these commands**:

#### ✅ To Keep the Changes:
```sql
COMMIT TRANSACTION;
```

#### ↩️ To Undo Everything:
```sql
ROLLBACK TRANSACTION;
```

---

## 📊 What Gets Updated

### Target Records:
- **Table:** `AttributeValue`
- **Attribute:** `IsActive` (ID: 4701)
- **Entity Type:** `AttributeMatrixItem` (Teaching Slides)
- **Current Value:** `'True'`
- **New Value:** `'False'`

### Preserved Metadata:
- `ModifiedDateTime` → **RETAINED** (to identify when file was uploaded)
- `ModifiedByPersonAliasId` → **RETAINED** (to identify who to contact for the missing file)

---

## ⚠️ Important Notes

1. **Don't close SSMS** while the transaction is open (it will auto-rollback)
2. **Don't run other queries** in the same window until you commit/rollback
3. **Transaction timeout:** SQL Server has default timeouts; don't leave it open indefinitely
4. **Safe to re-run:** The query only updates records where `Value = 'True'`, so it won't double-update
5. **Modified fields preserved:** The original `ModifiedDateTime` and `ModifiedByPersonAliasId` are intentionally kept so you know who uploaded the file and can contact them for the missing file

---

## 🔙 Rollback Instructions (If Needed Later)

If you need to undo this change after committing, use:

```sql
-- Restore all orphaned files back to IsActive = True
UPDATE av
SET av.Value = 'True'
FROM AttributeValue av
INNER JOIN AttributeValue av_file ON av_file.EntityId = av.EntityId
INNER JOIN orphaned_files o ON av_file.Value = CAST(o.BinaryFileGuid AS NVARCHAR(36))
WHERE av.AttributeId = 4701
  AND av.Value = 'False';

SELECT @@ROWCOUNT AS RowsRestored;
```

---

## 📝 Related Documentation

- `ORPHANED_FILES_TABLE.md` - Reference table of orphaned files
- `List of Deleted Files in Rock.csv` - Original source data
- `DeletedGuids 1.txt` - GUID list used to populate `orphaned_files` table

---

**Last Updated:** December 4, 2025  
**Contact:** IT Team / Rock RMS Admin

