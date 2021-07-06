## ssh
| | log example |
| ------ | ------ |
| Connection/Deconnection | Jun 2 03:32:04 eu-gva-backup-partner-0-c1699abf-1d23-ae39-3a34-e6673580f767 sshd[123133]: Accepted publickey for partner_uatlundbeck from 192.168.0.71 port 58294 ssh2: RSA SHA256:SHzKjEc2PuWF+QWH8L Received disconnect from 192.168.1.37 port 22:2: Too many authentication failures |
| Elevation de privilèges | Jun 17 14:33:48 BASTION sudo: pam_unix(sudo:session): session opened for user root by lisa(uid=0) |
|  Password failure for invalid/valid users | Feb 21 19:19:26 localhost sshd[16153]: Failed password for invalid user aurelien from 142.0.45.14 port 52772 ssh2  Feb 21 08:35:22 localhost sshd[5774]: Failed password for root from 116.31.116.24 port 29160 ssh2|
| Actions en ssh | Jun 17 14:33:43 BASTION sudo:   lorris : TTY=pts/0 ; PWD=/home/lorris ; USER=root ; COMMAND=/bin/cat COMMAND=/bin/ls |
| Création de groups | Feb 22 11:47:05 localhost groupadd[6991]: new group: name=docker_hack_group, GID=48 |
| Création de users | Feb 22 11:47:05 localhost useradd[6995]: new user: name=lorris_false_user, UID=48, GID=48, home=/usr/share/httpd, shell=/sbin/nologin |

## nginx/apache alerts
|  | lucene request |
| ------ | ------ |
| Web scrapping | [FREQUENCY ALERT] tags.keyword:apache-nginx_log and verb.keyword:GET and response.keyword:200  |

## ssh alerts
|  | lucene request |
| ------ | ------ |
|  Password failure for invalid/valid users | [FREQUENCY ALERT] sshd_valid_fail_user.keyword:* or sshd_invalid_fail_user.keyword:* |
| Création de users/groups | sshd_useradd_new_user_name.keyword:* or sshd_groupadd_new_group.keyword:* |
| Supression /ect/passwd | sshd_action_command.keyword : \"/bin/cat /etc/passwd\" |