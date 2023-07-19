# send syslog to special host:

  change rsyslog config and add below line to it (nano /etc/rsyslog.conf)
  
  *.* @@192.168.5.68:5144 // send all facility (first*) in all log level (second*) send to felan IP and port 
  
  or
  
  *.* @@192.168.5.68:5144:json-template // send all facility (first*) in all log level (second*) send to felan IP and port in json format
  
  if u use json, u must make a json tamplate file in /etc/rsyslog.d/01-json-template.conf
  @ for UDP and @@ for TCP 
  save and exit and then restart syslog service
  systemctl restart rsyslog
