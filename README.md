# README #

This README would normally document whatever steps are necessary to get your application up and running.

#How to install

Steps needed to create the necessary containers:-

1.Download the laradock folder from here 

https://drive.google.com/file/d/1yYmaU9eW_Qaxbm55iNMo904GHW4s8UvM/view?usp=sharing

(ps: for some reasons we can't upload the laradock folder in Bitbucket , so that's why we did this)

2.Paste it inside What_a_Trip folder

3.Go to the laradock folder inside What_a_Trip and open the .env file

4.Set the APP_CODE_PATH_HOST to the directory where the What_a_Trip folder is saved

5.Chose a directory for DATA_PATH_HOST where the docker container's data(like database) will be saved.
The docker client must have access to this directory

6.Save the env file

7.Now open the directory of What_a_Trip from your command promt

8.Go to laradock folder(cd laradock)

9.Run this command on the command prompt to create and open all the necessary containers:

docker-compose up -d nginx phpmyadmin mysql workspace redis
	
it will take some time to download the necessary libraries but once its done,it should successfully 
make the containers and show a notification on cmd

10.If all the above steps are done correctly you can now access our project from your browser by going to localhost

11.The phpmyadmin page can be accessed in localhost/8080 but if the port is blocked for some 
reason we can change it to another port

Exception-
To change the port of phpmyadmin follow step 1 first.Once inside the .env file find the PHPmyadmin section.

Change the PMA_PORT to a free port (8000 for example) and save.

You should be able to go to use phpmyadmin at localhost:8000 now

12.Every part of our project should function properly in this containerized environment
except for laravel dusk checking as it needs it's drivers to work(probably can be fixed soon 
if a dusk workable docker template)


Steps needed to run unit tests: 

1.Run the appropriate driver, chromedriver for linux operating system and chromedriver.exe for windows operating system.

2.Go to the What_a_Trip folder using the command prompt and type in the following code 

php artisan dusk
