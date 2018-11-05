# Outreachy-Task

The send email module is enabled with:

ceph mgr module enable sendemail

To execute the module, run:

ceph sendemail

Note before execute :
Gmail made some security change change recently. You now have to allow “less secure apps” on your account. Otherwise, you won’t be able to connect to it with your python script. 

also you must add your email and password also the target email ,subject and body before execute 

i want to write command in this format
```
COMMANDS = [
        {
            "cmd": "sendemail "
            "name= From_email,type=CephString,req=true"
            "name= Password_email,type=CephString,req=true"
            "name= to_email,type=CephString,req=true"
            "name= Subject_email,type=CephString,req=true"
            "name= body_email,type=CephString,req=true",       
            "desc": "send email",
            "perm": "rw"
        },
    ]
 ```
but i got error :
```
Traceback (most recent call last):
  File "/home/alaa/ceph/build/bin/ceph", line 1247, in <module>
    retval = main()
  File "/home/alaa/ceph/build/bin/ceph", line 1171, in main
    sigdict = parse_json_funcsigs(outbuf.decode('utf-8'), 'cli')
  File "/home/alaa/ceph/src/pybind/ceph_argparse.py", line 800, in parse_json_funcsigs
    cmd['sig'] = parse_funcsig(cmd['sig'])
  File "/home/alaa/ceph/src/pybind/ceph_argparse.py", line 729, in parse_funcsig
    raise JsonFormat(s)
ceph_argparse.JsonFormat: JSON descriptor [u'sendemail', {u'name': u''}, {u'req': u'truename=', u'type': u'CephString', u'name': u''}, {u'req': u'truename=', u'type': u'CephString', u'name': u''}, {u'req': u'truename=', u'type': u'CephString', u'name': u''}, {u'req': u'truename=', u'type': u'CephString', u'name': u''}, {u'req': u'true', u'type': u'CephString', u'name': u''}] has no type
```
