---
title: "v12.2.12 Luminous released"
date: "2019-04-12"
author: "TheAnalyst"
---

This is the twelfth bug fix release of the Luminous v12.2.x long term stable release series. We recommend that all users upgrade to this release.

## Notable Changes

- In 12.2.11 and earlier releases, keyring caps were not checked for validity, so the caps string could be anything. As of 12.2.12, caps strings are validated and providing a keyring with an invalid caps string to, e.g., ceph auth add will result in an error.

## Changelog

- auth: ceph auth add does not sanity-check caps ([issue#22525](https://tracker.ceph.com/issues/22525), [pr#24906](https://github.com/ceph/ceph/pull/24906), Jing Li, Nathan Cutler, Sage Weil)
- build/ops: Allow multi instances of “make tests” on the same machine ([issue#36737](https://tracker.ceph.com/issues/36737), [pr#26186](https://github.com/ceph/ceph/pull/26186), Kefu Chai)
- build/ops: rpm: require ceph-base instead of ceph-common ([issue#37620](https://tracker.ceph.com/issues/37620), [pr#25810](https://github.com/ceph/ceph/pull/25810), Sébastien Han)
- ceph-volume: add –all flag to simple activate ([pr#26656](https://github.com/ceph/ceph/pull/26656), Jan Fajerski)
- ceph-volume: look for rotational data in lsblk ([pr#26989](https://github.com/ceph/ceph/pull/26989), Andrew Schoen)
- ceph-volume: replace testinfra command with py.test ([pr#26824](https://github.com/ceph/ceph/pull/26824), Alfredo Deza)
- ceph-volume: revert partition as disk ([issue#37506](https://tracker.ceph.com/issues/37506), [pr#26295](https://github.com/ceph/ceph/pull/26295), Jan Fajerski)
- ceph-volume: simple scan will now scan all running ceph-disk OSDs ([pr#26857](https://github.com/ceph/ceph/pull/26857), Andrew Schoen)
- ceph-volume: use our own testinfra suite for functional testing ([pr#26703](https://github.com/ceph/ceph/pull/26703), Andrew Schoen)
- CLI: ability to change file ownership ([issue#38370](https://tracker.ceph.com/issues/38370), [pr#26758](https://github.com/ceph/ceph/pull/26758), Sébastien Han)
- client: session flush does not cause cap release message flush ([issue#38009](https://tracker.ceph.com/issues/38009), [pr#26271](https://github.com/ceph/ceph/pull/26271), Patrick Donnelly)
- common: ceph\_timer: stop timer’s thread when it is suspended ([issue#37766](https://tracker.ceph.com/issues/37766), [pr#26579](https://github.com/ceph/ceph/pull/26579), Peng Wang)
- common: fix for broken rbdmap parameter parsing ([issue#36327](https://tracker.ceph.com/issues/36327), [pr#26000](https://github.com/ceph/ceph/pull/26000), Marc Schoechlin)
- core: Objecter::calc\_op\_budget: Fix invalid access to extent union member ([issue#37932](https://tracker.ceph.com/issues/37932), [pr#26064](https://github.com/ceph/ceph/pull/26064), Simon Ruggier)
- core: os/filestore: ceph\_abort() on fsync(2) or fdatasync(2) failure ([issue#38258](https://tracker.ceph.com/issues/38258), [pr#26871](https://github.com/ceph/ceph/pull/26871), Sage Weil)
- crypto: don’t use PK11\_ImportSymKey() in FIPS mode ([issue#38843](https://tracker.ceph.com/issues/38843), [pr#27104](https://github.com/ceph/ceph/pull/27104), Radoslaw Zarzynski)
- Fix recovery and backfill priority handling ([issue#27985](https://tracker.ceph.com/issues/27985), [issue#38041](https://tracker.ceph.com/issues/38041), [pr#26793](https://github.com/ceph/ceph/pull/26793), Sage Weil, xie xingguo, David Zafman)
- journal: max journal order is incorrectly set at 64 ([issue#37541](https://tracker.ceph.com/issues/37541), [pr#25955](https://github.com/ceph/ceph/pull/25955), Mykola Golub)
- librgw: export multitenancy support ([issue#37928](https://tracker.ceph.com/issues/37928), [pr#25986](https://github.com/ceph/ceph/pull/25986), Tao Chen)
- mds: broadcast quota message to client when disable quota ([issue#38054](https://tracker.ceph.com/issues/38054), [pr#26293](https://github.com/ceph/ceph/pull/26293), Junhui Tang)
- mds: fix potential re-evaluate stray dentry in \_unlink\_local\_finish ([issue#38263](https://tracker.ceph.com/issues/38263), [pr#26473](https://github.com/ceph/ceph/pull/26473), Zhi Zhang)
- mds: handle fragment notify race ([issue#36035](https://tracker.ceph.com/issues/36035), [pr#25990](https://github.com/ceph/ceph/pull/25990), “Yan, Zheng”)
- mds: handle state change race ([issue#37594](https://tracker.ceph.com/issues/37594), [pr#26005](https://github.com/ceph/ceph/pull/26005), “Yan, Zheng”)
- mds: log evicted clients to clog/dbg ([issue#37639](https://tracker.ceph.com/issues/37639), [pr#25858](https://github.com/ceph/ceph/pull/25858), Patrick Donnelly)
- mds: log new client sessions with various metadata ([issue#37678](https://tracker.ceph.com/issues/37678), [pr#26257](https://github.com/ceph/ceph/pull/26257), Patrick Donnelly)
- mds: message invalid access ([issue#38488](https://tracker.ceph.com/issues/38488), [pr#26661](https://github.com/ceph/ceph/pull/26661), Patrick Donnelly)
- MDSMonitor: do not assign standby-replay when degraded ([issue#36384](https://tracker.ceph.com/issues/36384), [pr#26642](https://github.com/ceph/ceph/pull/26642), Patrick Donnelly)
- MDSMonitor: missing osdmon writeable check ([issue#37929](https://tracker.ceph.com/issues/37929), [pr#26065](https://github.com/ceph/ceph/pull/26065), Patrick Donnelly)
- mds: optimize revoking stale caps ([issue#38043](https://tracker.ceph.com/issues/38043), [pr#26278](https://github.com/ceph/ceph/pull/26278), “Yan, Zheng”)
- mds: stopping MDS with a large cache (40+GB) causes it to miss heartbeats ([issue#37723](https://tracker.ceph.com/issues/37723), [issue#38022](https://tracker.ceph.com/issues/38022), [pr#26232](https://github.com/ceph/ceph/pull/26232), Patrick Donnelly)
- mds: trim cache after journal flush ([issue#38010](https://tracker.ceph.com/issues/38010), [pr#26215](https://github.com/ceph/ceph/pull/26215), Patrick Donnelly)
- mds: wait for client to release shared cap when re-acquiring xlock ([issue#38491](https://tracker.ceph.com/issues/38491), [pr#27024](https://github.com/ceph/ceph/pull/27024), “Yan, Zheng”)
- mds: wait shorter intervals if beacon not sent ([issue#36367](https://tracker.ceph.com/issues/36367), [pr#25979](https://github.com/ceph/ceph/pull/25979), Patrick Donnelly)
- mgr: “balancer execute” only requires read permissions ([issue#25345](https://tracker.ceph.com/issues/25345), [pr#25768](https://github.com/ceph/ceph/pull/25768), John Spray)
- mgr/balancer: restrict automatic balancing to specific weekdays ([pr#26501](https://github.com/ceph/ceph/pull/26501), xie xingguo)
- mgr/BaseMgrModule: drop GIL for ceph\_send\_command ([issue#38537](https://tracker.ceph.com/issues/38537), [pr#26830](https://github.com/ceph/ceph/pull/26830), Sage Weil)
- mgr/DaemonServer: log pgmap usage to cluster log ([issue#37886](https://tracker.ceph.com/issues/37886), [pr#26207](https://github.com/ceph/ceph/pull/26207), Neha Ojha)
- mgr/dashboard: fix for using ‘::’ on hosts without ipv6 ([issue#38575](https://tracker.ceph.com/issues/38575), [pr#26751](https://github.com/ceph/ceph/pull/26751), Noah Watkins)
- mgr: deadlock: \_check\_auth\_rotating possible clock skew, rotating keys expired way too early ([issue#23460](https://tracker.ceph.com/issues/23460), [pr#26427](https://github.com/ceph/ceph/pull/26427), Yan Jun)
- mgr: drop GIL in get\_config ([issue#35985](https://tracker.ceph.com/issues/35985), [pr#26613](https://github.com/ceph/ceph/pull/26613), John Spray)
- mgr/restful: fix py got exception when get osd info ([issue#38182](https://tracker.ceph.com/issues/38182), [pr#26199](https://github.com/ceph/ceph/pull/26199), Boris Ranto, zouaiguo)
- mon: A PG with PG\_STATE\_REPAIR doesn’t mean damaged data, PG\_STATE\_IN… ([issue#38070](https://tracker.ceph.com/issues/38070), [pr#26305](https://github.com/ceph/ceph/pull/26305), David Zafman)
- mon/MgrStatMonitor: ensure only one copy of initial service map ([issue#38839](https://tracker.ceph.com/issues/38839), [pr#27207](https://github.com/ceph/ceph/pull/27207), Sage Weil)
- mon: monstore tool rebuild does not generate creating\_pgs ([issue#36306](https://tracker.ceph.com/issues/36306), [pr#25825](https://github.com/ceph/ceph/pull/25825), Sage Weil)
- mon: scrub warning check incorrectly uses mon scrub interval ([issue#37264](https://tracker.ceph.com/issues/37264), [pr#26557](https://github.com/ceph/ceph/pull/26557), Zhi Zhang, Sage Weil, David Zafman)
- msg/async: backport recent messenger fixes ([issue#36497](https://tracker.ceph.com/issues/36497), [issue#37778](https://tracker.ceph.com/issues/37778), [pr#25956](https://github.com/ceph/ceph/pull/25956), xie xingguo)
- msg/msg\_types: fix the dencoder of entity\_addr\_t ([issue#24676](https://tracker.ceph.com/issues/24676), [pr#26042](https://github.com/ceph/ceph/pull/26042), Kefu Chai)
- msgr: should set EPOLLET flag on del\_event() ([issue#38828](https://tracker.ceph.com/issues/38828), [pr#27226](https://github.com/ceph/ceph/pull/27226), Roman Penyaev)
- msg: should set EPOLLET flag on del\_event() ([issue#38857](https://tracker.ceph.com/issues/38857), [pr#27226](https://github.com/ceph/ceph/pull/27226), Roman Penyaev)
- multisite: es sync null versioned object failed because of olh info ([issue#23842](https://tracker.ceph.com/issues/23842), [issue#23841](https://tracker.ceph.com/issues/23841), [pr#26358](https://github.com/ceph/ceph/pull/26358), Tianshan Qu, Shang Ding)
- Object can still be deleted even if s3:DeleteObject policy is set ([issue#37403](https://tracker.ceph.com/issues/37403), [pr#26310](https://github.com/ceph/ceph/pull/26310), Enming.Zhang)
- objecter: avoid race when reset down osd’s session ([issue#24601](https://tracker.ceph.com/issues/24601), [pr#25853](https://github.com/ceph/ceph/pull/25853), Zengran Zhang)
- os/bluestore: backport new bitmap allocator ([issue#24598](https://tracker.ceph.com/issues/24598), [pr#26979](https://github.com/ceph/ceph/pull/26979), Radoslaw Zarzynski, Jianpeng Ma, Igor Fedotov, Sage Weil)
- os/bluestore: bitmap allocator might fail to return contiguous chunk despite having enough space ([issue#38761](https://tracker.ceph.com/issues/38761), [pr#27312](https://github.com/ceph/ceph/pull/27312), Igor Fedotov)
- os/bluestore: do not assert on non-zero err codes from compress() call ([issue#37839](https://tracker.ceph.com/issues/37839), [pr#26544](https://github.com/ceph/ceph/pull/26544), Igor Fedotov)
- os/bluestore: fix lack of onode ref during removal ([issue#38395](https://tracker.ceph.com/issues/38395), [pr#26540](https://github.com/ceph/ceph/pull/26540), Sage Weil)
- os/bluestore: Fix problem with bluefs’s freespace not being balanced when kv\_sync\_thread is sleeping ([issue#38574](https://tracker.ceph.com/issues/38574), [pr#26866](https://github.com/ceph/ceph/pull/26866), Adam Kupczyk)
- os/bluestore: fixup access a destroy cond cause deadlock or undefine ([issue#37733](https://tracker.ceph.com/issues/37733), [pr#26261](https://github.com/ceph/ceph/pull/26261), linbing)
- os/bluestore: KernelDevice::read() does the EIO mapping now ([issue#36455](https://tracker.ceph.com/issues/36455), [pr#25855](https://github.com/ceph/ceph/pull/25855), Radoslaw Zarzynski)
- osd: backport recent upmap fixes ([issue#37968](https://tracker.ceph.com/issues/37968), [issue#37940](https://tracker.ceph.com/issues/37940), [issue#37881](https://tracker.ceph.com/issues/37881), [pr#26127](https://github.com/ceph/ceph/pull/26127), huangjun, xie xingguo)
- osd: backport recent upmap fixes ([issue#38826](https://tracker.ceph.com/issues/38826), [issue#38897](https://tracker.ceph.com/issues/38897), [pr#27224](https://github.com/ceph/ceph/pull/27224), huangjun, xie xingguo)
- osd/bluestore: deep fsck fails on inspecting very large onodes ([issue#38065](https://tracker.ceph.com/issues/38065), [pr#26387](https://github.com/ceph/ceph/pull/26387), Igor Fedotov)
- OSD crashes in get\_str\_map while creating with ceph-volume ([issue#38329](https://tracker.ceph.com/issues/38329), [pr#26900](https://github.com/ceph/ceph/pull/26900), Sage Weil)
- osd: keep using cache even if op will invalid cache ([issue#37593](https://tracker.ceph.com/issues/37593), [pr#26078](https://github.com/ceph/ceph/pull/26078), Zengran Zhang)
- osd/PG.cc: account for missing set irrespective of last\_complete ([issue#37919](https://tracker.ceph.com/issues/37919), [pr#26236](https://github.com/ceph/ceph/pull/26236), Neha Ojha)
- osd/PrimaryLogPG: fix the extent length error of the sync read ([issue#37680](https://tracker.ceph.com/issues/37680), [pr#25711](https://github.com/ceph/ceph/pull/25711), Xiaofei Cui)
- osd/PrimaryLogPG: handle object !exists in handle\_watch\_timeout ([issue#38432](https://tracker.ceph.com/issues/38432), [pr#26706](https://github.com/ceph/ceph/pull/26706), Sage Weil)
- rbd-mirror: update mirror status when stopping ([issue#36659](https://tracker.ceph.com/issues/36659), [pr#25720](https://github.com/ceph/ceph/pull/25720), Jason Dillaman)
- rgw: bucket full sync handles delete markers ([issue#38007](https://tracker.ceph.com/issues/38007), [pr#26192](https://github.com/ceph/ceph/pull/26192), Casey Bodley)
- rgw: bucket limit check misbehaves for > max-entries buckets (usually 1000) ([issue#35973](https://tracker.ceph.com/issues/35973), [pr#26946](https://github.com/ceph/ceph/pull/26946), Matt Benjamin)
- rgw: bug in versioning concurrent, list and get have consistency issue ([issue#38060](https://tracker.ceph.com/issues/38060), [pr#26548](https://github.com/ceph/ceph/pull/26548), Wang Hao)
- rgw: check for non-existent bucket in RGWGetACLs ([issue#38116](https://tracker.ceph.com/issues/38116), [pr#26530](https://github.com/ceph/ceph/pull/26530), Matt Benjamin)
- rgw: data sync drains lease stack on lease failure ([issue#38479](https://tracker.ceph.com/issues/38479), [pr#26761](https://github.com/ceph/ceph/pull/26761), Casey Bodley)
- rgw: fails to start on Fedora 28 from default configuration ([issue#24228](https://tracker.ceph.com/issues/24228), [pr#26131](https://github.com/ceph/ceph/pull/26131), Matt Benjamin)
- rgw: feature – log successful bucket resharding events ([issue#37647](https://tracker.ceph.com/issues/37647), [pr#25738](https://github.com/ceph/ceph/pull/25738), J. Eric Ivancich)
- rgw: fetch\_remote\_obj filters out olh attrs ([issue#37792](https://tracker.ceph.com/issues/37792), [pr#26191](https://github.com/ceph/ceph/pull/26191), Casey Bodley)
- rgw: fix cls\_bucket\_head result order consistency ([issue#38410](https://tracker.ceph.com/issues/38410), [pr#26546](https://github.com/ceph/ceph/pull/26546), Tianshan Qu)
- rgw: fix radosgw linkage with WITH\_RADOSGW\_BEAST\_FRONTEND=OFF ([issue#23680](https://tracker.ceph.com/issues/23680), [pr#26332](https://github.com/ceph/ceph/pull/26332), Nathan Cutler)
- rgw: fix rgw\_data\_sync\_info::json\_decode() ([issue#38373](https://tracker.ceph.com/issues/38373), [pr#26549](https://github.com/ceph/ceph/pull/26549), Casey Bodley)
- rgw: handle S3 version 2 pre-signed urls with meta-data ([issue#23470](https://tracker.ceph.com/issues/23470), [pr#25901](https://github.com/ceph/ceph/pull/25901), Matt Benjamin)
- rgw: ldap: fix LDAPAuthEngine::init() when uri !empty() ([issue#38699](https://tracker.ceph.com/issues/38699), [pr#27173](https://github.com/ceph/ceph/pull/27173), Matt Benjamin)
- rgw: multiple es related fixes and improvements ([issue#22877](https://tracker.ceph.com/issues/22877), [issue#23655](https://tracker.ceph.com/issues/23655), [issue#38030](https://tracker.ceph.com/issues/38030), [issue#38028](https://tracker.ceph.com/issues/38028), [issue#36092](https://tracker.ceph.com/issues/36092), [pr#26516](https://github.com/ceph/ceph/pull/26516), Yehuda Sadeh, Abhishek Lekshmanan)
- rgw multisite: data sync checks empty next\_marker for datalog ([issue#39033](https://tracker.ceph.com/issues/39033), [pr#27299](https://github.com/ceph/ceph/pull/27299), Casey Bodley)
- rgw: nfs: skip empty (non-POSIX) path segments ([issue#38744](https://tracker.ceph.com/issues/38744), [pr#27180](https://github.com/ceph/ceph/pull/27180), Matt Benjamin)
- rgw: only update last\_trim marker on ENODATA ([issue#38075](https://tracker.ceph.com/issues/38075), [pr#26619](https://github.com/ceph/ceph/pull/26619), Casey Bodley)
- rgw: “radosgw-admin bucket rm … –purge-objects” can hang ([issue#38007](https://tracker.ceph.com/issues/38007), [issue#38134](https://tracker.ceph.com/issues/38134), [pr#26263](https://github.com/ceph/ceph/pull/26263), J. Eric Ivancich)
- rgw: rgw\_file: only first subuser can be exported to nfs ([issue#37855](https://tracker.ceph.com/issues/37855), [pr#26677](https://github.com/ceph/ceph/pull/26677), MinSheng Lin)
- rgw: rgwgc: process coredump in some special case ([issue#23199](https://tracker.ceph.com/issues/23199), [pr#25611](https://github.com/ceph/ceph/pull/25611), zhaokun)
- rgw: sse-c-fixes ([issue#38700](https://tracker.ceph.com/issues/38700), [pr#27295](https://github.com/ceph/ceph/pull/27295), Adam Kupczyk, Casey Bodley, Abhishek Lekshmanan)
- rgw: sync module: avoid printing attrs of objects in log ([issue#37646](https://tracker.ceph.com/issues/37646), [pr#27030](https://github.com/ceph/ceph/pull/27030), Abhishek Lekshmanan)
- tools: ceph-objectstore-tool: Dump hashinfo ([issue#37597](https://tracker.ceph.com/issues/37597), [pr#25722](https://github.com/ceph/ceph/pull/25722), David Zafman)