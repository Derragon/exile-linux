# exile-linux

These files are for installing the Exile mod on Linux servers. At this moment
the dependency installer only supports Ubuntu/Debian bt lowercase-exile script
(which lowercases the entire @Exile directory) will work on any Linux
distribution.

- Step 1: Run 'git clone https://github.com/Derragon/exile-linux.git"
- Step 2: Enter the "exile-linux" directory
- 	# cd exile-linux
- Step 3: Run sudo ./ubuntu-install-deps (Ubuntu only)
- Step 4: Download the client files and extract them to exile-server
- 	# wget http://exilecity.com/client/@Exile-0.9.6.zip
- 	# unzip @Exile-0.9.6.zip
- Step 5: Run ./lowercase-exile
- Step 6: Create a MySQL database and user with access.
- 	## EXAMPLE: ##
- 	mysql -u root -p (You'll need to enter your password)
- 	> create database exile;
- 	> create user 'exile' identified by 'password';
-	> grant all on exile.* to 'exile' identified by 'password;
-	> exit;
- Step 7: Edit the config files with your passwords/information.
-	In specific:
-		extdb-conf.ini (Enter the MySQL database/user/pass)
-		config.cfg (RCON password/server name)
-		BEServer.cfg (You'll need to rename BEServer.cfg.example)
- Step 8: Import the database into MySQL
-	# mysql -u exile -p exile < exile.sql
-	^ Use the password you created in Step 6
-
You're done! You can now launch your server with any of your preferred launch
script, or the one that has been provided.

./launch-server
