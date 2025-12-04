8:00 am - Christy contacted by Chris that files were missing
8:17 am - David Benson engaged to help investigate issue
8:20 am - William notified that blobs were deleted
8:30 am - William engaged to investigate
8:31 am - David Benson reported that this is out of scope for Foundation
9:03 am - SQL query showing binary file references in the database still existed on rockProd database
9:30am - After further discussion 
10:45 am - Ran SQL query on RockDev database, it showed no results
	- May be that a bad API request had been run against rockDev that deleted the blobs and the database references and left the database references untouched in rockProd
10:55 am - Started process to open support case with Microsoft Azure team to attempt recovery
11:17 am - First email confirmation received that support case was opened
11:17 am - David Benson engaged Bill to ask questions on guidance on issue
11:20 am - On chat with Microsoft Engineer
11:24 am - Started Teams call with Microsoft to discuss details of files to be recovered.
	- Engineer expected to give bi-hourly updates on recovery attempt
12:24 pm - Chris Tucker arrives, discussion around possibility for what could have happened with the AI agent
12:32 pm - Email update from Bill that this storage account is not under scope for Foundation team