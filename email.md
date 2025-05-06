# E-maily

Odesílání e-mailu přes SMTP pomocí Telnetu

```
telnet localhost 25
HELO localhost
MAIL FROM: pepa@localhost
RCPT TO: root@localhost
DATA
Subject: Testovaci
Ahoj svete
.
QUIT
```

# Mutt

> Klient pro čtení e-mailů v terminálu

```sh
apt install mutt
```

```sh
mutt -f ~root/Maildir
mutt -f /var/spool/mail/root
```

# Postfix

> Program pro příjem a odesílání e-mailů

```sh
apt install postfix
```

Přijímání e-mailů do maildiru

```
# /etc/postfix/main.cf
home_mailbox = Maildir/
mailbox_command =
```

Virtuální domény a e-maily a mapování na unix uživatele

```
# /etc/postfix/main.cf
virtual_alias_domains_map = hash:/etc/postfix/virtual_domains
virtual_alias_maps = hash:/etc/postfix/virtual
```

```
# /etc/postfix/virtual_domains
domena1.local	OK
domena2.local	OK
```

```
# /etc/postfix/virtual
info@domena1.local	root
info@domena2.local	root
```

```sh
postmap /etc/postfix/virtual_domains
postmap /etc/postfix/virtual
```
