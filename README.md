# check_jenkins_nodes
A Nagios/Opsview plug-in to monitor Jenkins slaves

## Help
```
$ ./check_jenkins_nodes --help
usage: check_jenkins_nodes [-h] [--version] -u USERNAME -p PASSWORD -U URL
                           [-w WARNING] [-c CRITICAL]

A Nagios/Opsview plug-in to monitor Jenkins slaves

optional arguments:
  -h, --help            show this help message and exit
  --version             show program's version number and exit
  -u USERNAME, --username USERNAME
                        username
  -p PASSWORD, --password PASSWORD
                        password
  -U URL, --url URL     Jenkins instance URL
  -w WARNING, --warning WARNING
                        warning threshold (default: 1)
  -c CRITICAL, --critical CRITICAL
                        critical threshold (default: 1)
```

## Example
```
$ ./check_jenkins_nodes -u jenkins -p password -U https://jenkins.company.com
CRITICAL - 1 offline node: jenkins-slave
$ echo $?
2
```

## 2 ways of excluding nodes from monitoring
1. When temporarily marking node offline, include `exclud` (case insensitive) anywhere in the offline reason field (e.g. `Temporarily excluded from monitoring - maintenance`)
2. To permanently exclude node from monitoring, include `exclud` (case insensitive) anywhere in the node's description field (e.g. `Build Slave - EXCLUDED`)

A number of offline nodes that have been excluded from monitoring will be appended to the plugin's output but it will not affect its exit code:
```
OK - All nodes are online (1 excluded)
```

