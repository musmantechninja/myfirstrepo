# myfirstrepo


* ### Expect Utility 
    
    The expect utility or scripting language works with scripts or programs that expect user inputs. It automates the task by providing inputs to expected outputs. Here is the expect script that we're using to automate the ssh login : 

    ```console
    #!/usr/bin/expect
    spawn ssh -o StrictHostKeyChecking=no user@server_ip
    expect "password"
    send "password"
    send "\r"
    interact
    ```
    Inorder for it to execute we need it installed. You may use the following command to install :
    ```console
    $  sudo apt-get install expect
    ```
