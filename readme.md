# Fail2ban apache actions

These are some apache fail2ban actions to block users based on apache
access deny settings.

Usually you do this using a firewall, however for some reason it's not working
too well on my current setup.

## Apache 2

Copy the `apache.conf` file into your `/etc/fail2ban/action.d/` directory, and activate
the action in the usual way. 

Next, add the following to your apache vhost `<Directory>` block:

```
<RequireAll>
    Require all granted
    Include /var/run/fail2ban/fail2ban.apache
</RequireAll>
```

## Apache 2.4 

Copy the `apache24.conf` file into your `/etc/fail2ban/action.d/` directory, and activate
the action in the usual way. 

Next, add the following to your apache vhost `<Directory>` block:

```
<RequireAll>
    Require all granted
    Include /var/run/fail2ban/fail2ban.apache24
</RequireAll>
```

## Mod-rewrite (not currently working)

Copy the `mod_rewrite.conf` file into your `/etc/fail2ban/action.d/` directory, and activate
the action in the usual way. 

