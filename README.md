<Additional Info for Windows users>
Windows users will need quite a bit of extra work:
    
### Easy Redis install:
```
https://redis.io/download 
```
roll the dice and run the .exe for server and cli 
(should be safe since its semi-trusted, but you never know)
(I used 3.2 but it doesn't really matter for this application)

### Many windows users will hit a wall with Channels.By downloading the appropriate binary and running pip install, you should be fine:
```
https://www.lfd.uci.edu/~gohlke/pythonlibs/#twisted
pip install c:/users/joe/downloads/Twisted‑18.7.0‑cp37‑cp37m‑win_amd64.whl  
```
e.g. if my computer username is joe and I save the file to downloads:
**be sure to check you have the correct version in the command**

### You may also be prompted to download Visual Studio C++ the error log will provide a link:
```
https://visualstudio.microsoft.com/downloads/
```
If this happens you ONLY need the build tools for C++!!
File sizes can get pretty big so start with the base recommendation (3 packages) and slowly add more (C++ related packages) if its still not working. 

### After installing redis windows users will get an error for win32api:
```
pip install pypiwin32
```

**********************************************************************************************
#### If this is your first time working with channels it is recommended to build the video's example exactly as is first, THEN tinker with the code. The app can be quite fragile with this set up so dont stress if things don't match up to the video, just go back a couple minutes and code-compare against the video.
**********************************************************************************************


<Original Readme>:

# Rapid-ChatXChannels
A rapid fire tutorial and introduction of Django Channels. To get more in-depth check out the full course https://kirr.co/badl8e

YouTube Video: https://www.youtube.com/watch?v=RVH05S1qab8&t=0s


### Recommended Start
```
$ cd path/to/your/dev/folder
$ mkdir channels-rapid
$ cd channels-rapid
$ git clone https://github.com/codingforentrepreneurs/Rapid-ChatXChannels .
$ git reset a9a2c42052c87fd2eb5acdc417729f9359a1e087 --hard
$ git remote remove origin
$ virtualenv -p python3 .
$ source bin/activate
(channels-rapid) $ cd src
(channels-rapid) $ pip install -r requirements.txt
(channels-rapid) $ python manage.py createsuperuser
... do the creation
(channels-rapid) $ python manage.py createsuperuser
... create second super user 
```


### Install Redis
1. Download Redis
    - Using [Homebrew](http://brew.sh):
        ```
        brew install redis

        brew services start redis
        ```
        Brew permission errors? Try `sudo chown -R "$USER":admin /usr/local`

    - Direct [Download](http://redis.io/download)

2. Open & Test Redis:
    - open Terminal

    - **redis-cli ping**
        ```
        $ redis-cli ping
        PONG
        ```

    - **redis-server**
        ```
        $ redis-server
        86750:C 08 Nov 08:17:21.431 # Warning: no config file specified, using the default config. In order to specify a config file use redis-server /path/to/redis.conf
        86750:M 08 Nov 08:17:21.433 * Increased maximum number of open files to 10032 (it was originally set to 256).
                        _._                                                  
                   _.-``__ ''-._                                             
              _.-``    `.  `_.  ''-._           Redis 3.2.5 (00000000/0) 64 bit
          .-`` .-```.  ```\/    _.,_ ''-._                                   
         (    '      ,       .-`  | `,    )     Running in standalone mode
         |`-._`-...-` __...-.``-._|'` _.-'|     Port: 6379
         |    `-._   `._    /     _.-'    |     PID: 86750
          `-._    `-._  `-./  _.-'    _.-'                                   
         |`-._`-._    `-.__.-'    _.-'_.-'|                                  
         |    `-._`-._        _.-'_.-'    |           http://redis.io        
          `-._    `-._`-.__.-'_.-'    _.-'                                   
         |`-._`-._    `-.__.-'    _.-'_.-'|                                  
         |    `-._`-._        _.-'_.-'    |                                  
          `-._    `-._`-.__.-'_.-'    _.-'                                   
              `-._    `-.__.-'    _.-'                                       
                  `-._        _.-'                                           
                      `-.__.-'                                               

        86750:M 08 Nov 08:17:21.434 # Server started, Redis version 3.2.5
        86750:M 08 Nov 08:17:21.434 * The server is now ready to accept connections on port 6379

        ```
        **Close Redis** with `control` + `c` to quit
