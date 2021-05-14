## Create a shell script that  prints hello word and that is sourced into Fluentd containter.

1. following script takes in put from environment variable.
    ```
      while true
      do echo hello >> /fluent/log
      sleep 10
      done
    ```  
    
 2.  Create a containter for fluentd, fluentd reads from the log and prints it in the console.
    
