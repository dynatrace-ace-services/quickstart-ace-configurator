# Maintenance Window : Day of month

You will create a daily maintenance window which will be enable at a specific `DayOfMonth` (1er day of month...) at the same period which starts at `MonthlyStart` and with the duration `DurationMinutes`.   
This maintenance window  will be enabled during `Star` to `End` period.  
This daily maintenance window is applied to the entities filtered by these 2 tags `app` and `env`    
On prerequisit, you need to git clone this repository and install monaco [here](https://github.com/dynatrace-ace-services/OnDemand-Configuration-with-Monaco#install-the-prebuild-configuration)
 
- export variables

      export NEW_CLI=1
      export MyTenant=<MyTenant>
      export MyToken=<MyToken>
      export Tag_app=<app>
      export Tag_env=<env>
      export DayOfMonth="1"
      export MonthlyStart="19:00"
      export DurationMinutes="720"
      export Start=`date +"%Y-%m-%d %H:%M"`
      export End=`date +"%Y-%m-%d %H:%M" -d "+10 year"`
      
- test variables

      echo "NEW_CLI="$NEW_CLI;echo "MyTenant=https://"$MyTenant;echo "MyToken="$MyToken;echo "Tag_app="$Tag_app;echo "Tag_env="$Tag_env;echo "DayOfMonth="$DayOfMonth;echo "MonthlyStart="$MonthlyStart;echo "DurationMinutes="$DurationMinutes;echo "Start="$Start;echo "End="$End
     
- deploy or update

      cd;cd quickstart-ace-configurator;
      ./monaco deploy -e=environments.yaml Maintenance-Window/deploy-dayofmonth-mw
      
- delete

      cd;cd quickstart-ace-configurator;
      echo " - \"maintenance-window/DayOfMonth="$DayOfMonth":"$Tag_app"_"$Tag_env"\"" >> Maintenance-Window/delete/delete.yaml;./monaco deploy -e=environments.yaml Maintenance-Window/delete;echo "delete:" > Maintenance-Window/delete/delete.yaml


# Result in Dynatrace 
- for this configuration  
       **Tag_app**=`easytravel03`  
       **Tag_env**=`sandbox`  
   
   <img src="https://user-images.githubusercontent.com/40337213/119020722-de457f80-b99e-11eb-8d67-ca976b609211.png" width="600" height="700">

