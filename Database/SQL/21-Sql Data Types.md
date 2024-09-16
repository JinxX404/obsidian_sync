الsql server فيه كذا كاتيجوري للداتا تايب 
- numeric
- decimal 
- char 
- datetime 
- binary 

##### numeric 

``` 
--bit   bool  0:1   true:false 
--tinyint		 1 byte       -128:+127  unsigned 0:255
--smallint		 2 byte	 -32768:+32767 unsigned 0:65555 
--int		   	 4 byte
--big int	   	 8 byte
```

- TINYINT
TINYINT is an 8-bit unsigned integer data type, representing small non-negative whole numbers.

**Range: 0 to 255.**

- **SMALLINT**
is a 16-bit signed integer data type suitable for smaller whole
numbers. 

**Range: -32,768 to 32,767.**

- **INT**
is a 32-bit signed integer data type used to store whole numbers without decimal places.

**Range: -2,147,483,648 to 2,147,483,647.**

- **BIGINT**
is a 64-bit signed integer data type, allowing the storage of larger whole numbers.

**Range: -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807.**


##### decimal 

##### char 

##### datetime 

##### binary 




```
--datatypes
--numeric
--bit   bool  0:1   true:false 
--tinyint		 1byte       -128:+127  unsigned 0:255
--smallint		 2b			  -32768:+32767 unsigned 0:65555 
--int		   	8b
--big int	   	2g
---------------------------
--decimale
--smallmoney 4b  .0000
--money      8b   .0000
--real			0.0000000
--float				0.0000000000000......
--dec dec(digits,floats) dec(5,2) 122.12    12.898 xx
------------------------------
--char  char(max number 10msln)  ficxed length chars reserved
--varchar(max number 10msln) variable length charachter by7gz 3la 2d ma tktb
--nchar()
--nvarchar() n for scability lw 3ayz aktb ai lo3'a 3'er el english
---------------------------------
--datetime
-- Date mm/dd/yyyy
--time hh:mm
--time(7) hh:mm 12.7875464
--smalldatetime modern dates mm/dd/yyy hh:mm
--datetime   more dates range
--datetime(7)
--datetimeoffset 24/11/2021 10:30 +2:00 time zone
--------------------------------
--binary 01110101
--image bttsave as binaries 


```