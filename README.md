# curltime
cURL formatted output

cURL supports formatted output for the details of the request ( see the cURL manpage for details, under “-w, –write-out <format>” ). 

My own custom format file (curl-format.txt) is provided for reference.

Next step is to create an Alias as follow: alias curltime="curl -w "@curl-format.txt" -o /dev/null -s"

> curltime www.github.xom

-w "@curl-format.txt" tells cURL to use our format file
-o /dev/null redirects the output of the request to /dev/null
-s tells cURL not to show a progress meter
   http://github.com/ is the URL we are requesting
   
   Here is the output: 
   
   =============  HOST:  ==========

          server_ip:  192.30.255.112
        server_port:  443

=======  CONNECTION:  ==========

          http_code:  301
       http_connect:  000
       num_connects:  1
      num_redirects:  0
       redirect_url:  https://github.com/

=============  FILE:  ==========

       content_type:
 filename_effective:  /dev/null
     ftp_entry_path:
      size_download:  0
        size_header:  103
       size_request:  78
        size_upload:  0
     speed_download:  0.000
       speed_upload:  0.000
  ssl_verify_result:  0
      url_effective:  https://www.github.com/

===  TIME BREAKDOWN:  ==========

    time_appconnect:  1.901
    time_TCPconnect:  0.782
     time_DNSlookup:  0.526
   time_pretransfer:  1.901
 time_starttransfer:  2.133
      time_redirect:  0.000
          time_TTFB:  2.133
                      ----------
         time_total:  2.133



Credit/Inspiration: http://blog.kenweiner.com/2014/11/http-request-timings-with-curl.html
