# WebDevelopment 
Today, I wasted 10 hours for installing apache&PHP environment...
  That was really struggled...
  
  But I find the server index of phpforwindows website: http://windows.php.net/downloads/releases/archives/
  A millions of php version at here!
  
  Just keep followings in mind:
  
  1.The versions of Apache files must be coincident with PHP files 
    Both thread safe and same vc compiler complied files.(later apache version is good, but php cannot. )
    (apache 2.2 -> vc9/or former version -> vs2008)  (apache2.4 -> vc 11 maybe...) vc11->vs2012| vc14->vs2015.
  
  2.change apache httpd.conf file:
      This guy has the same stupid problem as me ... Anyway, the bolg was fantistic.  
      https://my.oschina.net/idearye/blog/192265 
      
      * put the following codes into this file:
         LoadModule php5_module ${PATH}/php5apache2_2.dll
         PHPIniDir ${PATH} (or: like this: "E:\WebDevelopment\php-5.6.26-nts-Win32-VC11-x64")
         AddType application/x-httpd-php .php .html .htm (add MINI Types)
         
      * test apache httpd.conf file syntax correctness:
          Open Cmd as Administrator, input: "APACHE_PATH\bin\httpd.exe" -t
          
        * add apache server               : "APACHE_PATH\bin\httpd.exe" -k install -n apache (-n stand for naming the server as apache)
        * delete apache server            : sc delete apache 
        * look the port cmd               : netstat -a
        
      *  Change DirectoryIndex Value in conf file.
          DirectoryIndex index.php index.html
          
      *  Chagen Document root:
          define PHPdeveRoot "E:\WebDevelopment\projectFolder"
          DocumentRoot "${PHPdeveRoot}/htdocs"
          <Directory "${PHPdeveRoot}/htdocs">
        ... ...
   3. Configure php environment :
      
      * find the php installing root and change 'php-ini-development' into 'php-ini'
      
      * in the php.ini file: 
            ;This file generally configure the php sys-envri for many options, if some error you cannot find in any ways, find this file.  

         *   extension_dir = "./" into extension_dir = "{PHP_PATH}\ext"
　　　　　　　　extension=php_curl.dll
　　　　　　　　extension=php_gd2.dll
　　　　　　　　extension=php_mbstring.dll
　　　　　　　　extension=php_mysql.dll
　　　　　　　　extension=php_xmlrpc.dll      
              date.timezone = Asia/Shanghai OR Eourpen/London ...
              short_open_tag = Off into On
              display_errors = Off into On #Easier for find error    
              set error_reporting  value as E_ALL 
              register_argc_argv = On  OR register_globals = On
              #    WHEN( register_globals=Off) 
              #       $_POST['user_name'], $_POST['user_pass'] are more complicitied...
              #    HOWEVER, WHEN( register_globals=On)
              #       WE could use  $user_name,$user_pass this type varible for geting value.
          
          *   A short code for test mysql db connectivity
              <?php
              $host = "localhost";
              $user = "root";
              $password = "123";//123改成你的mysql密码
              $link=mysql_connect($host,$user,$password); 
              if(!$link) echo "<h1>失败!</h1>";
              else echo "<h1>成功!</h1>";
              mysql_close();
              ?>
          *   phpinfo(); Print all info about environment.
          
      * The file included in the Windows directory is same as which be wirten into 'path' environment system options.
          if we do not want to include the php path in path sys-enr variables,
          alternatively, we can copy php.ini into C:Windows directory and copy php5ts.dll into directory C:Windows\system32
          
      
      
        
        
        
