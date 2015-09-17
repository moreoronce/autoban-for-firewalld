## README

1. Clone and Place autoban.py at where u want  

<code> git clone git@github.com:moreoronce/autoban-for-firewalld.git </code>

<code>cd autoban-for-firewalld </code>

<code>mv autoban.py ~</code>


2. Install Supervisor    

Install supervisor via pip or yum or apt

3. Edit supervisord.conf  

Add these 3 lines to supervisord.conf   

<code>log_stdout=true</code>
<code>log_stderr=true</code>
<code>logfile=/var/log/shadowsocks.log</code>


4. Edit rc.local to make it automake    

Add these 2 lines to rc.local  

<code>python ~/autoban.py < /var/log/shadowsocks.log</code>
<code>nohup tail -F /var/log/shadowsocks.log | python ~/autoban.py 1>/dev/null 2>&1 &</code>

5. Done