## Python has a super useful tool for serving files over HTTP. 
    This is great if you just want to create a quick network share that other machines on your network can access.
    To do that just go to the directory you want to share and run:

    $ python -m SimpleHTTPServer
    This sets up a basic webserver that you can access via the localhost address. 
    So grab the IP address of the machine you ran this on and then on another machine access it 
    in the browser with: http://IP_ADDRESS:8000. On your own machine, you can view the files available by typing: http://localhost:8000 in your web browser.
