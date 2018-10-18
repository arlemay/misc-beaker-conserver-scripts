# misc-beaker-conserver-scripts
scripts I have collected and wrote for beaker and conserver and a few other things.


Conserver scripts

ibm-hmc-ssh-special

Used for connecting to p9 lpars with conserver and HMC 

From my conserver.cf

default ibm-hmc-ssh-special {
       type exec;
       execsubst Q=hs,%=rs;
       exec /usr/local/lib/conserver/ibm-hmc-ssh-special $HMCHOSTNAME $HMCUSER $PASSWORD % $SYSTEMNAME;
}


After the definitions 

console $hostname-lp1.example.com  { include ibm-hmc-ssh-special; host $HMCHOSTNAME; replstring lp1; }
console $HOSTNAME-lp2.example.com  { include ibm-hmc-ssh-special; host $HMCHOSTNAME; replstring lp2; }
console $HOSTNAME-lp3.example.com  { include ibm-hmc-ssh-special; host $HMCHOSTNAME; replstring lp3; }
console $HOSTNAME-lp4.example.com  { include ibm-hmc-ssh-special; host $HMCHOSTNAME; replstring lp4; 
 
