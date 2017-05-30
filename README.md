# check_jenkins_nodes
A Nagios/Opsview plug-in to monitor Jenkins slaves

## Help
```
./check_jenkins_nodes --help
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
