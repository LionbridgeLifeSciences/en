# Restore Backup Files to the Self-built MySQL Service

You can restore the backup data of the MySQL service to the self-built database.

## Precautions
* The self-built database version shall be consistent with the source database version of backup files.
* The backup unzipping software can only be used in Linux.
* System software of unzipping tools relies on openssl, gzip, tee and python, with version >= 2.7.
* The current system has already been installed with percona xtrabackup >= 2.4; If not, please refer to [Official Manual](https://www.percona.com/doc/percona-xtrabackup/2.4/index.html).

## Operation Instructions
1. See the requirements for installation environment in precautions.
2. Download backup unzipping tools, [Click to Download](http://jddb-common-public.s-bj.jcloud.com/mysql_backup_extract_tool.tar.gz) and unzip. The tool name is `mysql_backup_extract.py`, and the using instances are as follows.
    
    ```
    # View Help Manual
    ./percona_backup_extract.py -h
     
     # Unzipping backup data of Percona service instance
     ./percona_backup_extract.py  -v 5.7 -f ./backup.xbstream.gz.enc
    ```
3. Download backup files.

    ```
    wget -c ‘<Data backup download link>' -O <Customized backup file name>.xbstream.gz.enc

    -c: Start breakpoint upload
    -O: Save downloaded results as the assigned files and note that the suffix of files must be .xbstream.gz.enc
    ```

4. Unzip the backup data, and the unzipped files will be saved in tmp_snapshot, a sub-directory of the current directory, assuming that the current directory is $HOME.

    ```
    ./mysql_backup_extract.py -v 5.6 -f <Customized backup file name>.xbstream.gz.enc
    
    -v Parameters may not be assigned, the default value is 5.6, and view the -h Help Manual for details of variables following -v.
    ```

5. Restore the unzipped backup files.

    ```
    innobackupex --defaults-file=$HOME/tmp_snapshot/backup-my.cnf --apply-log $HOME/tmp_snapshot
    ``` 
    ***innobackupex completed OK!*** indicates successful execution, and you can continue to the next step.

6. Modify the configuration file, backup-my.cnf.

    ```
    # The MySQL server
    [mysqld]
    innodb_checksum_algorithm=innodb
    #innodb_log_checksum_algorithm=strict_crc32
    innodb_data_file_path=ibdata1:512M;ibdata2:512M:autoextend
    innodb_log_files_in_group=3
    innodb_log_file_size=536870912
    #innodb_fast_checksum=false
    #innodb_page_size=16384
    #innodb_log_block_size=512
    innodb_undo_directory=.
    innodb_undo_tablespaces=0
    #redo_log_version=1
    ```

7. Modify the file owner and confirm that files are owned by the MySQL user.

    ```
    chown -R mysql:mysql $HOME/tmp_snapshot
    ```

8. Start the MySQL process.

    ```
    mysqld_safe --defaults-file=$HOME/tmp_snapshot/backup-my.cnf --user=mysql --datadir=$HOME/tmp_snapshot &
    ```

9. Login the MySQL service.

    ```
    mysql -uroot -p
    ```

* Click "Enter" directly due to the default blank password.
