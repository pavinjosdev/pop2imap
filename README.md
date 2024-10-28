# pop2imap
Backup of pop2imap from http://www.linux-france.org/prj/pop2imap/dist/

# Required dependencies on Debian 12
```
libmail-pop3client-perl
libemail-simple-perl
libdate-manip-perl
```

# Usage
```
usage: /usr/bin/pop2imap [options]

Several options are mandatory. See the example below.

--from        <string> : parsed as <user1>@<host1>[:<port1>]
--host1       <string> : "from" POP server. Mandatory.
--port1       <int>    : port to connect. Default is 110 (ssl:995).
--user1       <string> : user to login.   Mandatory.
--password1   <string> : password for the user1. Dangerous, use --passfile1
--passfile1   <string> : password file for the user1. Contains the password.
--ssl1                 : enable ssl on POP connect
--to          <string> : parsed as <user2>@<host2>[:<port2>][/<folder>]
--host2       <string> : "destination" IMAP server. Mandatory.
--port2       <int>    : port to connect. Default is 143 (ssl:993).
--user2       <string> : user to login.   Mandatory.
--password2   <string> : password for the user2. Dangerous, use --passfile2
--passfile2   <string> : password file for the user2. Contains the password.
--ssl2                 : enable ssl on IMAP connect
--starttls2            : use starttls on IMAP connect instead of SSL
--timeout2    <int>    : Connections timeout in seconds. Default is 240.
--folder      <string> : sync to this IMAP folder.
--delete               : delete messages in "from" POP server after
                         a successful transfer. useful in case you
                         want to migrate from one server to another one.
                         They are really deleted when a QUIT command
                         is send.
--idatefromheader      : sets the internal dates on host2 same as the 
                         "Date:" headers from host1. Turned on by default.
--dry                  : do nothing, just print what would be done.
--debug                : debug mode.
--debugimap            : IMAP debug mode.
--debugpop             : POP debug mode.
--tests                : Run non-regression tests
--quiet                : Only print error messages
--version              : print sotfware version.
--help                 : print this message.

  pop2imap license is "No limits to do anything with this work and this license."

Example: to synchronise pop  account "test1" on "test1.lamiral.info"
                     to imap account "test2" on "test2.lamiral.info"

/usr/bin/pop2imap \
   --host1 test1.lamiral.info --ssl1 --user1 test1 --password1 "secret1" \
   --host2 test2.lamiral.info --ssl2 --user2 test2 --password2 "secret2"

 $Id: pop2imap,v 1.32 2020/12/24 18:29:21 gilles Exp gilles $ 
```
