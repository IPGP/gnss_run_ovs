# gnssposflow
Frontend shell programs to run GNSS processing with GipsyX.  
Written initially for volcano deformation monitoring, but designed to be polyvalent and ready-to-use.

## gnss_run_gipsyx
Simple bash scripts to run JPL/GipsyX software and produce routine automatic PPP daily solutions from GNSS observation archives.

To get help:
```bash
./gnss_run_gipsyx
      Syntax: gnss_run_gipsyx CONF DAYS [options]
 Description: runs the automatic GNSS process from raw files to position solution
   Arguments:
       CONF = configuration filename (see gnss_run_gipsyx_template.rc)
       DAYS = number of days to process (from today)
     Options:
       -s "STA1 STA2..."
        station code or station list with double quotes
           default is all nodes defined in CONF variable NODES=
       -d "yyyy/mm/dd,yyyy/mm/dd"
        choose days to start process; the DAYS argument can still be used to
        process previous days from the selected ones, for instance:
        gnss_run_gipsyx CONF 1 -d 2017/03/17,2018/08/05
        will compute  2017/03/17, 2017/03/16, 2018/08/05 and 2018/08/04
       -final, -rapid, -ultra
        use only final, rapid or ultra orbit
       -force
        forces the process despite existence of final results
       -lock
        creates a lock file to prevent multiple process of gnss_run_gipsyx
       -debug
        verbose mode & temporary folders will not be deleted
       -fullog
        Full log record. Temporary folders are stored in a .fullog.7z file (7-zip needed)
```

### Note
Initial scripts have been developed as part of the [WebObs System](https://ipgp.github.io/webobs/), where you might find older versions. New scripts are fully independent from WebObs. It remains only the possibility to get a list of stations from WebObs grid's nodes, andthe  default solution file structure and syntax still corresponds to the WebObs GipsyX input data format.

### Authors
François BEAUDUCEL, Edgar LENHOF, Patrice BOISSIER, Pierre SAKIC
