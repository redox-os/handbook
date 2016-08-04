# Netcat

nc utility is a clone of original Netcat often called the TCP/IP swiss army knife.
It can be used to create only outbound TCP connections for now.

## Usage

**Outbound connection:**

Assuming you have obtained an IP address (with `dhcpd`) and there is some server
listening (e.g. another instance of `nc` running on the machine which you are
  using to run Redox), you can connect to it with nc.

* Host machine:
```
$ nc -l -p 15000
```

* Redox guest:
```
$ nc 10.0.2.2:15000
```

**Send file across network:**

If you want to send a file from Redox into your host operating system, you can easily use nc in order to do that:

* Set up host OS to listen for a file transfer
```
$ nc -l -p 30000 > file_name
```

* Send a file from Redox
```
$ nc 10.0.2.2:30000 < file_name
```

[Go Back](index.md)
