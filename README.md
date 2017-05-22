# curltime
cURL formatted output

cURL supports formatted output for the details of the request ( see the cURL manpage for details, under “-w, –write-out <format>” ). 

My own custom format file (curl-format.txt) is provided for reference.

Next step is to create an Alias as follow: alias curltime="curl -w "@curl-format.txt" -o /dev/null -s"

> curltime https://pbs.twimg.com/profile_images/798943583784968192/zTRX1owc_400x400.jpg 

-w "@curl-format.txt" tells cURL to use our format file
-o /dev/null redirects the output of the request to /dev/null
-s tells cURL not to show a progress meter
   http://github.com/ is the URL we are requesting
   
   Here is the output: 
   
=============  HOST:  ==========

          server_ip:  117.18.237.70
        server_port:  443

=======  CONNECTION:  ==========

          http_code:  200
       http_connect:  000
       num_connects:  1
      num_redirects:  0
       redirect_url:

=============  FILE:  ==========

       content_type:  image/jpeg
       filename_effective:  /dev/null
     ftp_entry_path:
      size_download:  18023
        size_header:  574
       size_request:  131
        size_upload:  0
     speed_download:  29278.000
       speed_upload:  0.000
       ssl_verify_result:  0
      url_effective:  https://pbs.twimg.com/profile_images/798943583784968192/zTRX1owc_400x400.jpg

===  TIME BREAKDOWN:  ==========

    time_appconnect:  0.601
    time_TCPconnect:  0.522
     time_DNSlookup:  0.518
     time_pretransfer:  0.601
 time_starttransfer:  0.613
      time_redirect:  0.000
          time_TTFB:  0.613
                      ----------
         time_total:  0.616



Credit/Inspiration: http://blog.kenweiner.com/2014/11/http-request-timings-with-curl.html
