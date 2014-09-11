auto-resize-data-fs
------

Opinionated script to automatically manage the size of a single LV
with a known filesystem type.

Designed with the intention that all data will be stored in this LV, mounted
under /data (though this is not prescribed here)

If new storage is added to the machine as an 'sd' device, it will be claimed
by this VG, and the data LV extended to utilise the new space.

A 'reserved PE percentage' (default 10%) can be used to keep some space unallocated,
largely to allow for snapshot LVs to be created, but also can be handy in emergency situations.

Use of LVM to handle multiple spindles is enforced - it gives a common set of operations and
gives useful benefits when handling detachable storage such as vCD independent disks or AWS
EBS volumes.


