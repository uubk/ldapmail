# LDAPMail
This repository includes a working draft of a LDAP schema for mail. It uses the
SOSETH OID (1.3.6.1.4.1.25725.\*) space, so if you fork this please change the
OID.

# Warning: Work in progess
The LDAP schema is not finished and subject to be changed! LDAP schema evolution
is rather convoluted, you have been warned!

## Usage
You might want to have a look at `files/schema.ldif`. Each user is expected to
use `mailboxPerson` as an additional object type. There should be exactly one
object with type `virtualDomain` which is supposed to contain all virtual
domains. Groups can get `mailGroup` as an additional type, in which case they
can get an alias that should automatically be delivered to all members.
The default settings are configured for [uubk/auth-server](https://github.com/uubk/auth-server) on the LDAP side and [SOSETH/mailserver](https://github.com/SOSETH/mailserver)
on the postfix/dovecot side.
