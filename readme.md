
**Clone 3 repositories**   
  
add new hosts  
  

    127.0.0.1 rates.localhost  
    127.0.0.1 rates-front.localhost  

**Backend**
  
Put 3 folder on the same path level   
Go to docker-setup folder and run:   

    docker-compose build  
    docker-compose up -d  

 
  
Go to launchpad container:  
  

    docker exec -it rates_launchpad bash  

> 
  

    cd /otp/rates  

  >

    composer install  

copy env file:  
  

    cp env.example .env  

  
add these rows in the .env  
  

    PUSHER_APP_ID=1778308  
    PUSHER_APP_KEY=19a3ac5559975feae007  
    PUSHER_APP_SECRET=058f64ac3321b90881c2  
    PUSHER_APP_CLUSTER=eu  

  

    #API DATA  
    API_URL=https://api.monobank.ua/bank/currency  
      
    DB_CONNECTION=sqlite    
    BROADCAST_CONNECTION=pusher

  
run:  
  
`php artisan migrate`  -  to create sqlite file  
  
change file owner (if needed ) and permission  

    chown -R :www-data  database/database.sqlite  
    chmod -R 775 database.sqlite  

  
change storage file/folders permissions   

    chmod -R 777 storage/*  

  
run: command `php artisan schedule:work` in the background  
  
  **Front end**
  
duplicate terminal , go to /opt/rates-frontend  
  

    run: npm install  

  
open browser  

    rates.localhost:3000

  
  
  
**How is it working** 
  
  I am using Pusher service to send events t 
  Data will be updated every 5 minutes
