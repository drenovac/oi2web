// how to setup environment

1. create table OI2WEB (perhaps DATAVOL).
   In the code I refer to MMSCSTM (we attach this as our generic volume for application control )
1. The code has 2 inserts, which are the local generic application equates - comment them out &
   insert local EQU if anything fails
   $INSERT nv_copyright
   $INSERT nv_userprefs

2. change the win_id	= "MMS**.." to reflect the local repos & window name

3. open oi2web.init - locate the commented out call to 'GOSUB create_table'
////////////////////////////////////////////////////////////////////////////////
// uncomment this on first install of table for DICT layout
// once created - no need to re-exec this.
// this is a bit sloppy in sequence, but once setup no need to go back
////////////////////////////////////////////////////////////////////////////////
//	GOSUB create_table:

CLEARFILE oi$f ELSE

4. Once this runs once, comment back the GOSUB create_table line

// oi2web.json

This code creates the .json extract, and places it into "f:\temp\.."
Change this to your local path
