-- Install Instructions --

Step 1: Download the repository
    # git clone https://github.com/Derragon/exile-linux.git
    
Step 2: Download and unpack SteamCMD (If you haven't already, run: 'sudo apt-get install lib32gcc1')
    # wget https://steamcdn-a.akamaihd.net/client/installer/steamcmd_linux.tar.gz
    # tar zxvf steamcmd_linux.tar.gz
    
Step 3: Install Arma 3 Server (You need to login to SteamCMD with your account)
    # ./steamcmd.sh
    # login username password
    # force_install_dir exile-linux
    # app_update 233780 validate
    # exit
    
Step 4: Enter the 'exile-linux' directory and run the 'ubuntu-install-deps' script
    # cd exile-linux
    # sudo ./ubuntu-install-deps
    Note: Must be run with sudo
    
Step 5: Download the Client files and unpack them
    # wget http://exilecity.com/client/@Exile-0.9.6.zip
    # unzip @Exile-0.9.6.zip
    
Step 6: Run the lowercase-exile script
    # ./lowercase-exile
    
Step 7: Create the MySQL Database and User
    # mysql -u root -p (You will be prompted to enter your password
    # > create database exile;
    # > create user 'exile' identified by 'password';
    # > grant all on exile.* to 'exile' identified by 'password';
    
Step 8: Import the database file into MySQL
    # mysql -u exile -p exile < exile.sql
    Replace the first 'exile' with your username, the second 'exile' with your database
    You will be prompted to enter your password.
    
Step 9: Edit the config files to your needs

    -- @ExileServer/config.cfg --
    * passwordAdmin must be changed
    * serverCommandPassword must be changed
    
    -- battleye/BEServer.cfg --
    * Password must be changed
    
    -- @ExileServer/extdb-conf.ini --
    * Password must be changed to the same password that's in BEServer.cfg
    * Name must be changed to whichever database you created
    * User must be changed the user you created
    * Password is the password you used for that user
    
Step 10: You're done! You can now either run ./launch-server or download your own script for launching/managing the server.
Output is logged by default to stderr.log and stdout.log
