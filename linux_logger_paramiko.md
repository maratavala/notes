#### Issue:  Below code snippet is not writing the message 'Hello' to file /var/log/messages in the host  

from paramiko import SSHClient, AutoAddPolicy  
sshconn = SSHClient()  
sshconn.set_missing_host_key_policy(AutoAddPolicy())  
sshconn.connect(hostname, port, username, key_filename)  
stdin, stdout, stderr = sshconn.exec_command('/bin/logger Hello', get_pty=True)  
sshconn.close()  

#### Solution:  Remove get_pty  

stdin, stdout, stderr = sshconn.exec_command('/bin/logger Hello')  
