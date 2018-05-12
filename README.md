# utl_displaying_almost_all_sas_wps_date_and_time_formats_with_sample_default_values
Displaying almost all sas wps date and time formats with sample default values. Keywords: sas sql join merge big data analytics macros oracle teradata mysql sas communities stackoverflow statistics artificial inteligence AI Python R Java Javascript WPS Matlab SPSS Scala Perl C C# Excel MS Access JSON graphics maps NLP natural language processing machine learning igraph DOSUBL DOW loop stackoverflow SAS community.
    Displaying almost all SAS/WPS date and time formats with sample default values

    Thanks Nat and Richard

    Nat Wooding
    nathani@verizon.net

    Richard DeVenezia
    http://www.devenezia.com/downloads/sas/samples/


    What SAS can turn a float into is amazing, just think of what SAS could do with
    a 128bit float. Encryption, Random Numbers, Big Int, UUIDGEN, Fast big HASH,
    more accurate datetime, much longer,precision, better convergence....

    github
    https://tinyurl.com/y7gjhe6k
    https://github.com/rogerjdeangelis/utl_displaying_almost_all_sas_wps_date_and_time_formats_with_sample_default_values

      WPS seemed to match SAS except for these six, may be as simple as removing the 'x'.
      But I am too lazy.
      Eyeballing the results they looked the same.

         DDMMYYx.
         MMDDYYx.
         MMYYx.
         YYMMx.
         YYMMDDx.
         YYQx.
         YYQRx.

    Thanks Nat abd Richard for the list

    Nat Wooding
    nathani@verizon.net

    Richard DeVenezia
    http://www.devenezia.com/downloads/sas/samples/


    INPUT
    =====

    YYQRxw      TIMEAMPMw    $N8601Bw     DAYw       HHMMw
    $N8601BAw   TODw         $N8601BAw    DDMMYYw    HOURw
    $N8601Ew    WEEKDATEw    $N8601Ew     DDMMYYxw   JULDAYw
    $N8601EAw   WEEKDATXw    $N8601EAw    DOWNAMEw   JULIANw
    $N8601EHw   WEEKDAYw     $N8601EHw    DTDATEw    MMDDYYw
    $N8601EXw   WEEKUw       $N8601EXw    DTMONYYw   MMDDYYxw
    $N8601Hw    WEEKVw       $N8601Hw     DTWKDATXw  MMSSw
    $N8601Xw    WEEKWw       $N8601Xw     DTYEARw    MMYYw
    B8601DAw    WORDDATEw    B8601DAw     DTYYQCw    MMYYxw
    B8601DNw    WORDDATXw    B8601DNw     E8601DAw   MONNAMEw
    B8601DTw    YEARw        B8601DTw     E8601DNw   MONTHw
    B8601DZw    YYMMw        B8601DZw     E8601DTw   MONYYw
    B8601LZw    YYMMxw       B8601LZw     E8601DZw   PDJULGw
    B8601TMw    YYMMDDw      B8601TMw     E8601LZw   PDJULIw
    B8601TZw    YYMMDDxw     B8601TZw     E8601TMw   QTRw
    E8601DAw    YYMONw       DATEw        E8601TZw   QTRRw
    E8601DNw    YYQw         DATEAMPMw    YYQRw      TIMEw
    E8601DTw    YYQxw        E8601LZw
    E8601DZw


    PROCESS  ( this is input/process/output)
    ==========================================

    data want;
    informat dteFmt $16.;
    input dteFmt @@;
    if not (dteFmt=:'$') then res=left(putn(today(),dteFmt));
    else res=left(putc('0002405050112FFC',dteFmt));
    cards4;
    $N8601B. $N8601BA. $N8601E. $N8601EA. $N8601EH. $N8601EX. $N8601H. $N8601X.
    B8601DA. B8601DN. B8601DT. B8601DZ. B8601LZ. B8601TM. B8601TZ. DATE. DATEAMPM.
    DATETIME. DAY. DDMMYY. DDMMYYx. DOWNAME. DTDATE. DTMONYY. DTWKDATX. DTYEAR.
    DTYYQC. E8601DA. E8601DN. E8601DT. E8601DZ. E8601LZ. E8601TM. E8601TZ. HHMM.
    HOUR. JULDAY. JULIAN. MMDDYY. MMDDYYx. MMSS. MMYY. MMYYx. MONNAME. MONTH. MONYY.
    PDJULG. PDJULI. QTR. QTRR. TIME. TIMEAMPM. TOD. WEEKDATE. WEEKDATX. WEEKDAY.
    WEEKU. WEEKV. WEEKW. WORDDATE. WORDDATX. YEAR. YYMM. YYMMx. YYMMDD. YYMMDDx.
    YYMON. YYQ. YYQx. YYQR. YYQRx. $N8601BA. $N8601E. $N8601EA. $N8601EH. $N8601EX.
    $N8601H. $N8601X. B8601DA. B8601DN. B8601DT. B8601DZ. B8601LZ. B8601TM. B8601TZ.
    E8601DA. E8601DN. E8601DT. E8601DZ. E8601LZ. E8601TM. E8601TZ.
    ;;;;
    run;quit;


    OUTPUT
    ======

    WORK.WANT total obs=92

    Obs    DTEFMT       RES

      1    $N8601B.     P2Y4M5DT5H1M12S
      2    $N8601BA.    P00020405T050112
      3    $N8601E.     P2Y4M5DT5H1M12S
      4    $N8601EA.    P0002-04-05T05:01:12
      5    $N8601EH.    P0002-04-05T05:01:12
      6    $N8601EX.    P0002-04-05T05:01:12
      7    $N8601H.     P2Y4M5DT5H1M12S
      8    $N8601X.     P2Y4M5DT5H1M12S
      9    B8601DA.     20180512
     10    B8601DN.     19600101
     11    B8601DT.     19600101T055516
     12    B8601DZ.     19600101T055516+0000
     13    B8601LZ.     055516-0400
     14    B8601TM.     055516
     15    B8601TZ.     055516+0000
     16    DATE.        12MAY18
     17    DATEAMPM.    01JAN60:05:55:16 AM
     18    DATETIME.    01JAN60:05:55:16
     19    DAY.         12
     20    DDMMYY.      12/05/18
     21    DDMMYYx.     21316
     22    DOWNAME.     Saturday
     23    DTDATE.      01JAN60
     24    DTMONYY.     JAN60
     25    DTWKDATX.    Friday, 1 January 1960
     26    DTYEAR.      1960
     27    DTYYQC.      60:1
     28    E8601DA.     2018-05-12
     29    E8601DN.     1960-01-01
     30    E8601DT.     1960-01-01T05:55:16
     31    E8601DZ.     1960-01-01T05:55:16+00:00
     32    E8601LZ.     05:55:16-04:00
     33    E8601TM.     05:55:16
     34    E8601TZ.     05:55:16+00:00
     35    HHMM.        5:55
     36    HOUR.        6
     37    JULDAY.      132
     38    JULIAN.      18132
     39    MMDDYY.      05/12/18
     40    MMDDYYx.     21316
     41    MMSS.        355
     42    MMYY.        05M2018
     43    MMYYx.       21316
     44    MONNAME.     May
     45    MONTH.       5
     46    MONYY.       MAY18
     47    PDJULG.      /
     48    PDJULI.      /
     49    QTR.         2
     50    QTRR.        II
     51    TIME.        5:55:16
     52    TIMEAMPM.    5:55:16 AM
     53    TOD.         05:55:16
     54    WEEKDATE.    Saturday, May 12, 2018
     55    WEEKDATX.    Saturday, 12 May 2018
     56    WEEKDAY.     7
     57    WEEKU.       2018-W18-07
     58    WEEKV.       2018-W19-06
     59    WEEKW.       2018-W19-06
     60    WORDDATE.    May 12, 2018
     61    WORDDATX.    12 May 2018
     62    YEAR.        2018
     63    YYMM.        2018M05
     64    YYMMx.       21316
     65    YYMMDD.      18-05-12
     66    YYMMDDx.     21316
     67    YYMON.       2018MAY
     68    YYQ.         2018Q2
     69    YYQx.        21316
     70    YYQR.        2018QII
     71    YYQRx.       21316
     72    $N8601BA.    P00020405T050112
     73    $N8601E.     P2Y4M5DT5H1M12S
     74    $N8601EA.    P0002-04-05T05:01:12
     75    $N8601EH.    P0002-04-05T05:01:12
     76    $N8601EX.    P0002-04-05T05:01:12
     77    $N8601H.     P2Y4M5DT5H1M12S
     78    $N8601X.     P2Y4M5DT5H1M12S
     79    B8601DA.     20180512
     80    B8601DN.     19600101
     81    B8601DT.     19600101T055516
     82    B8601DZ.     19600101T055516+0000
     83    B8601LZ.     055516-0400
     84    B8601TM.     055516
     85    B8601TZ.     055516+0000
     86    E8601DA.     2018-05-12
     87    E8601DN.     1960-01-01
     88    E8601DT.     1960-01-01T05:55:16
     89    E8601DZ.     1960-01-01T05:55:16+00:00
     90    E8601LZ.     05:55:16-04:00
     91    E8601TM.     05:55:16
     92    E8601TZ.     05:55:16+00:00

    ;;;;

    BONUS

    Richard DeVenezia

    http://www.devenezia.com/downloads/sas/samples/

    DATE5.     -> 09FEB
    DATE6.     ->  09FEB
    DATE7.     -> 09FEB10
    DATE8.     ->  09FEB10
    DATE9.     -> 09FEB2010
    DATE11.    -> 09-FEB-2010

    DAY.       ->  9
    DAY3.      ->   9
    DAY4.      ->    9
    DAY5.      ->     9

    DDMMYY.    -> 09/02/10
    DDMMYY2.   -> 09
    DDMMYY3.   ->  09
    DDMMYY4.   -> 0902
    DDMMYY5.   -> 09/02
    DDMMYY6.   -> 090210
    DDMMYY7.   ->  090210
    DDMMYY8.   -> 09/02/10
    DDMMYY9.   ->  09/02/10
    DDMMYY10.  -> 09/02/2010

    DDMMYY.    -> 09/02/10
    DDMMYYB2.  -> 09
    DDMMYYB3.  ->  09
    DDMMYYB4.  -> 0902
    DDMMYYB5.  -> 09 02
    DDMMYYB6.  -> 090210
    DDMMYYB7.  ->  090210
    DDMMYYB8.  -> 09 02 10
    DDMMYYB9.  ->  09 02 10
    DDMMYYB10. -> 09 02 2010
    DDMMYYC2.  -> 09
    DDMMYYC3.  ->  09
    DDMMYYC4.  -> 0902
    DDMMYYC5.  -> 09:02
    DDMMYYC6.  -> 090210
    DDMMYYC7.  ->  090210
    DDMMYYC8.  -> 09:02:10
    DDMMYYC9.  ->  09:02:10
    DDMMYYC10. -> 09:02:2010
    DDMMYYD2.  -> 09
    DDMMYYD3.  ->  09
    DDMMYYD4.  -> 0902
    DDMMYYD5.  -> 09-02
    DDMMYYD6.  -> 090210
    DDMMYYD7.  ->  090210
    DDMMYYD8.  -> 09-02-10
    DDMMYYD9.  ->  09-02-10
    DDMMYYD10. -> 09-02-2010
    DDMMYYN2.  -> 09
    DDMMYYN3.  ->  09
    DDMMYYN4.  -> 0902
    DDMMYYN5.  ->  0902
    DDMMYYN6.  -> 090210
    DDMMYYN7.  ->  090210
    DDMMYYN8.  -> 09022010
    DDMMYYP2.  -> 09
    DDMMYYP3.  ->  09
    DDMMYYP4.  -> 0902
    DDMMYYP5.  -> 09.02
    DDMMYYP6.  -> 090210
    DDMMYYP7.  ->  090210
    DDMMYYP8.  -> 09.02.10
    DDMMYYP9.  ->  09.02.10
    DDMMYYP10. -> 09.02.2010
    DDMMYYS2.  -> 09
    DDMMYYS3.  ->  09
    DDMMYYS4.  -> 0902
    DDMMYYS5.  -> 09/02
    DDMMYYS6.  -> 090210
    DDMMYYS7.  ->  090210
    DDMMYYS8.  -> 09/02/10
    DDMMYYS9.  ->  09/02/10
    DDMMYYS10. -> 09/02/2010

    DOWNAME.   ->   Tuesday
    DOWNAME1.  -> T
    DOWNAME2.  -> Tu
    DOWNAME3.  -> Tue
    DOWNAME4.  -> Tues
    DOWNAME5.  -> Tuesd
    DOWNAME6.  -> Tuesda
    DOWNAME7.  -> Tuesday
    DOWNAME8.  ->  Tuesday
    DOWNAME9.  ->   Tuesday
    DOWNAME10. ->    Tuesday
    DOWNAME11. ->     Tuesday

    EURDFDD.   -> 09.02.10
    EURDFDD2.  -> 09
    EURDFDD3.  ->  09
    EURDFDD4.  -> 0902
    EURDFDD5.  -> 09.02
    EURDFDD6.  -> 090210
    EURDFDD7.  ->  090210
    EURDFDD8.  -> 09.02.10

    EURDFDE.   -> 09FEB10
    EURDFDE5.  -> 09FEB
    EURDFDE6.  ->  09FEB
    EURDFDE7.  -> 09FEB10
    EURDFDE8.  ->  09FEB10
    EURDFDE9.  -> 09FEB2010

    EURDFDN.   -> 2
    EURDFDN1.  -> 2
    EURDFDN2.  ->  2
    EURDFDN3.  ->   2
    EURDFDN4.  ->    2

    EURDFDWN.  ->   Tuesday
    EURDFDWN1. -> T
    EURDFDWN2. -> Tu
    EURDFDWN3. -> Tue
    EURDFDWN4. -> Tues
    EURDFDWN5. -> Tuesd
    EURDFDWN6. -> Tuesda
    EURDFDWN7. -> Tuesday
    EURDFDWN8. ->  Tuesday
    EURDFDWN9. ->   Tuesday
    EURDFDWN10.->    Tuesday

    EURDFMN.   ->  February
    EURDFMN1.  -> F
    EURDFMN2.  -> Fe
    EURDFMN3.  -> Feb
    EURDFMN4.  -> Febr
    EURDFMN5.  -> Febru
    EURDFMN6.  -> Februa
    EURDFMN7.  -> Februar
    EURDFMN8.  -> February
    EURDFMN9.  ->  February
    EURDFMN10. ->   February
    EURDFMN11. ->    February

    EURDFMY.   -> FEB10
    EURDFMY5.  -> FEB10
    EURDFMY6.  ->  FEB10
    EURDFMY7.  -> FEB2010

    EURDFWDX.  ->    9 February 2010
    EURDFWDX17.->        9 Feb 2010
    EURDFWDX18.->    9 February 2010
    EURDFWDX19.->     9 February 2010
    EURDFWDX20.->      9 February 2010
    EURDFWDX21.->       9 February 2010

    EURDFWKX.  ->      Tuesday, 9 February 2010
    EURDFWKX3. -> Tue
    EURDFWKX4. ->  Tue
    EURDFWKX5. ->   Tue
    EURDFWKX6. ->    Tue
    EURDFWKX7. ->     Tue
    EURDFWKX8. ->      Tue
    EURDFWKX9. ->   Tuesday
    EURDFWKX10.->    Tuesday
    EURDFWKX11.->     Tuesday
    EURDFWKX12.->      Tuesday
    EURDFWKX13.->       Tuesday
    EURDFWKX14.->        Tuesday
    EURDFWKX15.->   Tue, 9 Feb 10
    EURDFWKX16.->    Tue, 9 Feb 10
    EURDFWKX17.->   Tue, 9 Feb 2010
    EURDFWKX18.->    Tue, 9 Feb 2010
    EURDFWKX19.->     Tue, 9 Feb 2010
    EURDFWKX20.->      Tue, 9 Feb 2010
    EURDFWKX21.->       Tue, 9 Feb 2010
    EURDFWKX22.->        Tue, 9 Feb 2010
    EURDFWKX23.->     Tuesday, 9 Feb 2010
    EURDFWKX24.->      Tuesday, 9 Feb 2010

    JULDAY.    ->  40
    JULDAY3.   ->  40
    JULDAY4.   ->   40
    JULDAY5.   ->    40
    JULDAY6.   ->     40
    JULDAY7.   ->      40
    JULDAY8.   ->       40

    JULIAN.    -> 10040
    JULIAN5.   -> 10040
    JULIAN6.   ->  10040
    JULIAN7.   -> 2010040

    MINGUO.    -> 99/02/09
    MINGUO1.   -> *
    MINGUO2.   -> 99
    MINGUO3.   -> 099
    MINGUO4.   -> 9902
    MINGUO5.   -> 99/02
    MINGUO6.   -> 990209
    MINGUO7.   ->  990209
    MINGUO8.   -> 99/02/09
    MINGUO9.   ->  99/02/09
    MINGUO10.  -> 0099/02/09

    MMDDYY.    -> 02/09/10
    MMDDYY2.   -> 02
    MMDDYY3.   ->  02
    MMDDYY4.   -> 0209
    MMDDYY5.   -> 02/09
    MMDDYY6.   -> 020910
    MMDDYY7.   ->  020910
    MMDDYY8.   -> 02/09/10

    MMDDYY.    -> 02/09/10
    MMDDYYB2.  -> 02
    MMDDYYB3.  ->  02
    MMDDYYB4.  -> 0209
    MMDDYYB5.  -> 02 09
    MMDDYYB6.  -> 020910
    MMDDYYB7.  ->  020910
    MMDDYYB8.  -> 02 09 10
    MMDDYYB9.  ->  02 09 10
    MMDDYYB10. -> 02 09 2010
    MMDDYYC2.  -> 02
    MMDDYYC3.  ->  02
    MMDDYYC4.  -> 0209
    MMDDYYC5.  -> 02:09
    MMDDYYC6.  -> 020910
    MMDDYYC7.  ->  020910
    MMDDYYC8.  -> 02:09:10
    MMDDYYC9.  ->  02:09:10
    MMDDYYC10. -> 02:09:2010
    MMDDYYD2.  -> 02
    MMDDYYD3.  ->  02
    MMDDYYD4.  -> 0209
    MMDDYYD5.  -> 02-09
    MMDDYYD6.  -> 020910
    MMDDYYD7.  ->  020910
    MMDDYYD8.  -> 02-09-10
    MMDDYYD9.  ->  02-09-10
    MMDDYYD10. -> 02-09-2010
    MMDDYYN2.  -> 02
    MMDDYYN3.  ->  02
    MMDDYYN4.  -> 0209
    MMDDYYN5.  ->  0209
    MMDDYYN6.  -> 020910
    MMDDYYN7.  ->  020910
    MMDDYYN8.  -> 02092010
    MMDDYYP2.  -> 02
    MMDDYYP3.  ->  02
    MMDDYYP4.  -> 0209
    MMDDYYP5.  -> 02.09
    MMDDYYP6.  -> 020910
    MMDDYYP7.  ->  020910
    MMDDYYP8.  -> 02.09.10
    MMDDYYP9.  ->  02.09.10
    MMDDYYP10. -> 02.09.2010
    MMDDYYS2.  -> 02
    MMDDYYS3.  ->  02
    MMDDYYS4.  -> 0209
    MMDDYYS5.  -> 02/09
    MMDDYYS6.  -> 020910
    MMDDYYS7.  ->  020910
    MMDDYYS8.  -> 02/09/10
    MMDDYYS9.  ->  02/09/10
    MMDDYYS10. -> 02/09/2010

    MMYY.      -> 02M2010
    MMYY5.     -> 02M10
    MMYY6.     ->  02M10
    MMYY7.     -> 02M2010
    MMYY8.     ->  02M2010
    MMYY9.     ->   02M2010
    MMYY10.    ->    02M2010

    MMYY.      -> 02M2010
    MMYYC5.    -> 02:10
    MMYYC6.    ->  02:10
    MMYYC7.    -> 02:2010
    MMYYC8.    ->  02:2010
    MMYYC9.    ->   02:2010
    MMYYC10.   ->    02:2010
    MMYYC11.   ->     02:2010
    MMYYD5.    -> 02-10
    MMYYD6.    ->  02-10
    MMYYD7.    -> 02-2010
    MMYYD8.    ->  02-2010
    MMYYD9.    ->   02-2010
    MMYYD10.   ->    02-2010
    MMYYN5.    ->  0210
    MMYYN6.    -> 022010
    MMYYN7.    ->  022010
    MMYYN8.    ->   022010
    MMYYN9.    ->    022010
    MMYYP5.    -> 02.10
    MMYYP6.    ->  02.10
    MMYYP7.    -> 02.2010
    MMYYP8.    ->  02.2010
    MMYYS5.    -> 02/10
    MMYYS6.    ->  02/10
    MMYYS7.    -> 02/2010
    MMYYS8.    ->  02/2010

    MONNAME.   ->  February
    MONNAME1.  -> F
    MONNAME2.  -> Fe
    MONNAME3.  -> Feb
    MONNAME4.  -> Febr
    MONNAME5.  -> Febru
    MONNAME6.  -> Februa
    MONNAME7.  -> Februar
    MONNAME8.  -> February
    MONNAME9.  ->  February

    MONTH.     ->  2
    MONTH1.    -> 2
    MONTH2.    ->  2
    MONTH3.    ->   2

    MONYY.     -> FEB10
    MONYY5.    -> FEB10
    MONYY6.    ->  FEB10
    MONYY7.    -> FEB2010

    NENGO.     -> H.22/02/09
    NENGO2.    -> 22
    NENGO3.    -> H22
    NENGO4.    -> H.22
    NENGO5.    -> H2202
    NENGO6.    -> H22/02
    NENGO7.    -> H220209
    NENGO8.    -> H.220209
    NENGO9.    -> H22/02/09
    NENGO10.   -> H.22/02/09

    PDJULG.    ->  
    PDJULG3.   -> ??
    PDJULG4.   ->  
    PDJULG5.   ->   
    PDJULG6.   ->    
    PDJULG7.   ->     
    PDJULG8.   ->      

    PDJULI.    -> 
    PDJULI3.   -> ??
    PDJULI4.   -> 
    PDJULI5.   ->  
    PDJULI6.   ->   
    PDJULI7.   ->    
    PDJULI8.   ->     
    PDJULI9.   ->      

    QTR.       -> 1
    QTR1.      -> 1
    QTR2.      ->  1
    QTR3.      ->   1

    QTRR.      ->   I
    QTRR3.     ->   I
    QTRR4.     ->    I
    QTRR5.     ->     I
    QTRR6.     ->      I

    WEEKDATE.  ->     Tuesday, February 9, 2010
    WEEKDATE3. -> Tue
    WEEKDATE4. ->  Tue
    WEEKDATE5. ->   Tue
    WEEKDATE6. ->    Tue
    WEEKDATE7. ->     Tue
    WEEKDATE8. ->      Tue
    WEEKDATE9. ->   Tuesday
    WEEKDATE10.->    Tuesday
    WEEKDATE11.->     Tuesday
    WEEKDATE12.->      Tuesday
    WEEKDATE13.->       Tuesday
    WEEKDATE14.->        Tuesday
    WEEKDATE15.->  Tue, Feb 9, 10
    WEEKDATE16.->   Tue, Feb 9, 10
    WEEKDATE17.->  Tue, Feb 9, 2010
    WEEKDATE18.->   Tue, Feb 9, 2010
    WEEKDATE19.->    Tue, Feb 9, 2010
    WEEKDATE20.->     Tue, Feb 9, 2010
    WEEKDATE21.->      Tue, Feb 9, 2010
    WEEKDATE22.->       Tue, Feb 9, 2010
    WEEKDATE23.->    Tuesday, Feb 9, 2010
    WEEKDATE24.->     Tuesday, Feb 9, 2010

    WEEKDATX.  ->      Tuesday, 9 February 2010
    WEEKDATX3. -> Tue
    WEEKDATX4. ->  Tue
    WEEKDATX5. ->   Tue
    WEEKDATX6. ->    Tue
    WEEKDATX7. ->     Tue
    WEEKDATX8. ->      Tue
    WEEKDATX9. ->   Tuesday
    WEEKDATX10.->    Tuesday
    WEEKDATX11.->     Tuesday
    WEEKDATX12.->      Tuesday
    WEEKDATX13.->       Tuesday
    WEEKDATX14.->        Tuesday
    WEEKDATX15.->   Tue, 9 Feb 10
    WEEKDATX16.->    Tue, 9 Feb 10
    WEEKDATX17.->   Tue, 9 Feb 2010
    WEEKDATX18.->    Tue, 9 Feb 2010
    WEEKDATX19.->     Tue, 9 Feb 2010
    WEEKDATX20.->      Tue, 9 Feb 2010
    WEEKDATX21.->       Tue, 9 Feb 2010
    WEEKDATX22.->        Tue, 9 Feb 2010
    WEEKDATX23.->     Tuesday, 9 Feb 2010
    WEEKDATX24.->      Tuesday, 9 Feb 2010
    WEEKDATX25.->       Tuesday, 9 Feb 2010

    WEEKDAY.   -> 3
    WEEKDAY1.  -> 3
    WEEKDAY2.  ->  3
    WEEKDAY3.  ->   3

    WORDDATE.  ->   February 9, 2010
    WORDDATE3. -> Feb
    WORDDATE4. ->  Feb
    WORDDATE5. ->   Feb
    WORDDATE6. ->    Feb
    WORDDATE7. ->     Feb
    WORDDATE8. ->      Feb
    WORDDATE9. ->  February
    WORDDATE10.->   February
    WORDDATE11.->    February
    WORDDATE12.->  Feb 9, 2010
    WORDDATE13.->   Feb 9, 2010
    WORDDATE14.->    Feb 9, 2010
    WORDDATE15.->     Feb 9, 2010
    WORDDATE16.->      Feb 9, 2010
    WORDDATE17.->       Feb 9, 2010
    WORDDATE18.->   February 9, 2010
    WORDDATE19.->    February 9, 2010

    WORDDATX.  ->    9 February 2010
    WORDDATX3. -> Feb
    WORDDATX4. ->  Feb
    WORDDATX5. ->   Feb
    WORDDATX6. ->    Feb
    WORDDATX7. ->     Feb
    WORDDATX8. ->      Feb
    WORDDATX9. ->  February
    WORDDATX10.->   February
    WORDDATX11.->    February
    WORDDATX12.->   9 Feb 2010
    WORDDATX13.->    9 Feb 2010
    WORDDATX14.->     9 Feb 2010
    WORDDATX15.->      9 Feb 2010
    WORDDATX16.->       9 Feb 2010
    WORDDATX17.->        9 Feb 2010
    WORDDATX18.->    9 February 2010
    WORDDATX19.->     9 February 2010
    WORDDATX20.->      9 February 2010

    YEAR.      -> 2010
    YEAR2.     -> 10
    YEAR3.     ->  10
    YEAR4.     -> 2010
    YEAR5.     ->  2010
    YEAR6.     ->   2010

    YYMM.      -> 2010M02
    YYMM5.     -> 10M02
    YYMM6.     ->  10M02
    YYMM7.     -> 2010M02
    YYMM8.     ->  2010M02
    YYMM9.     ->   2010M02

    YYMM.      -> 2010M02
    YYMMC5.    -> 10:02
    YYMMC6.    ->  10:02
    YYMMC7.    -> 2010:02
    YYMMC8.    ->  2010:02
    YYMMC9.    ->   2010:02
    YYMMD5.    -> 10-02
    YYMMD6.    ->  10-02
    YYMMD7.    -> 2010-02
    YYMMD8.    ->  2010-02
    YYMMD9.    ->   2010-02
    YYMMD10.   ->    2010-02
    YYMMN5.    ->  1002
    YYMMN6.    -> 201002
    YYMMN7.    ->  201002
    YYMMN8.    ->   201002
    YYMMN9.    ->    201002
    YYMMN10.   ->     201002
    YYMMN11.   ->      201002
    YYMMP5.    -> 10.02
    YYMMP6.    ->  10.02
    YYMMP7.    -> 2010.02
    YYMMP8.    ->  2010.02
    YYMMP32.   ->

    YYMMS5.    -> 10/02
    YYMMS6.    ->  10/02
    YYMMS7.    -> 2010/02

    YYMMDD.    -> 10-02-09
    YYMMDD2.   -> 10
    YYMMDD3.   ->  10
    YYMMDD4.   -> 1002
    YYMMDD5.   -> 10-02
    YYMMDD6.   -> 100209
    YYMMDD7.   ->  100209
    YYMMDD8.   -> 10-02-09

    YYMMDD.    -> 10-02-09
    YYMMDDB2.  -> 10
    YYMMDDB3.  ->  10
    YYMMDDB4.  -> 1002
    YYMMDDB5.  -> 10 02
    YYMMDDB6.  -> 100209
    YYMMDDB7.  ->  100209
    YYMMDDB8.  -> 10 02 09
    YYMMDDB9.  ->  10 02 09
    YYMMDDB10. -> 2010 02 09
    YYMMDDC2.  -> 10
    YYMMDDC3.  ->  10
    YYMMDDC4.  -> 1002
    YYMMDDC5.  -> 10:02
    YYMMDDC6.  -> 100209
    YYMMDDC7.  ->  100209
    YYMMDDC8.  -> 10:02:09
    YYMMDDC9.  ->  10:02:09
    YYMMDDC10. -> 2010:02:09
    YYMMDDD2.  -> 10
    YYMMDDD3.  ->  10
    YYMMDDD4.  -> 1002
    YYMMDDD5.  -> 10-02
    YYMMDDD6.  -> 100209
    YYMMDDD7.  ->  100209
    YYMMDDD8.  -> 10-02-09
    YYMMDDD9.  ->  10-02-09
    YYMMDDD10. -> 2010-02-09
    YYMMDDN2.  -> 10
    YYMMDDN3.  ->  10
    YYMMDDN4.  -> 1002
    YYMMDDN5.  ->  1002
    YYMMDDN6.  -> 100209
    YYMMDDN7.  ->  100209
    YYMMDDN8.  -> 20100209
    YYMMDDP2.  -> 10
    YYMMDDP3.  ->  10
    YYMMDDP4.  -> 1002
    YYMMDDP5.  -> 10.02
    YYMMDDP6.  -> 100209
    YYMMDDP7.  ->  100209
    YYMMDDP8.  -> 10.02.09
    YYMMDDP9.  ->  10.02.09
    YYMMDDP10. -> 2010.02.09
    YYMMDDS2.  -> 10
    YYMMDDS3.  ->  10
    YYMMDDS4.  -> 1002
    YYMMDDS5.  -> 10/02
    YYMMDDS6.  -> 100209
    YYMMDDS7.  ->  100209
    YYMMDDS8.  -> 10/02/09
    YYMMDDS9.  ->  10/02/09
    YYMMDDS10. -> 2010/02/09

    YYMON.     -> 2010FEB
    YYMON5.    -> 10FEB
    YYMON6.    ->  10FEB
    YYMON7.    -> 2010FEB
    YYMON8.    ->  2010FEB
    YYMON9.    ->   2010FEB
    YYMON10.   ->    2010FEB

    YYQ.       -> 2010Q1
    YYQ4.      -> 10Q1
    YYQ5.      ->  10Q1
    YYQ6.      -> 2010Q1
    YYQ7.      ->  2010Q1

    YYQ.       -> 2010Q1
    YYQC4.     -> 10:1
    YYQC5.     ->  10:1
    YYQC6.     -> 2010:1
    YYQC7.     ->  2010:1
    YYQC8.     ->   2010:1
    YYQD4.     -> 10-1
    YYQD5.     ->  10-1
    YYQD6.     -> 2010-1
    YYQD7.     ->  2010-1
    YYQD8.     ->   2010-1
    YYQD9.     ->    2010-1
    YYQD10.    ->     2010-1

    YYQN4.     ->  101
    YYQN5.     -> 20101
    YYQN6.     ->  20101
    YYQN7.     ->   20101
    YYQP4.     -> 10.1
    YYQP5.     ->  10.1
    YYQP6.     -> 2010.1
    YYQP7.     ->  2010.1
    YYQS4.     -> 10/1
    YYQS5.     ->  10/1
    YYQS6.     -> 2010/1
    YYQS7.     ->  2010/1

    YYQR.      ->   2010QI
    YYQR6.     -> 2010QI
    YYQR7.     ->  2010QI

    YYQR.      ->   2010QI
    YYQRC6.    -> 2010:I
    YYQRC7.    ->  2010:I
    YYQRD6.    -> 2010-I
    YYQRD7.    ->  2010-I
    YYQRN6.    ->  2010I
    YYQRN7.    ->   2010I
    YYQRN8.    ->    2010I
    YYQRP6.    -> 2010.I
    YYQRP7.    ->  2010.I
    YYQRS6.    -> 2010/I
    YYQRS7.    ->  2010/I
    YYQRS8.    ->   2010/I


