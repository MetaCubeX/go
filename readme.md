# MeteCubeX forked Go

## Revert Golang1.26 commit for Windows7/8
this patch file only works on golang1.26.x

that means after golang1.27 release it must be changed

see: https://github.com/MetaCubeX/go/commits/release-branch.go1.26/

revert:
* 693def151adff1af707d82d28f55dba81ceb08e1: "crypto/rand,runtime: switch RtlGenRandom for ProcessPrng"
* 7c1157f9544922e96945196b47b95664b1e39108: "net: remove sysSocket fallback for Windows 7"
* 48042aa09c2f878c4faa576948b07fe625c4707a: "syscall: remove Windows 7 console handle workaround"
* a17d959debdb04cd550016a3501dd09d50cd62e7: "runtime: always use LoadLibraryEx to load system libraries"

sepical fix:
- os.RemoveAll not working on Windows7
```shell
cd $(go env GOROOT)
curl https://github.com/MetaCubeX/go/commit/b0d48afabb9fd14976c27221cb525c5d2ebbfe79.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/44e76f7cf1bc6e04b5da724e0b2e48f393713506.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/b4aece36e51ecce81c3ee9fe03e31db552e90018.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/ea2726a6fa25fbfa1092e696e522eafca544d24c.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/d47e0d22130d597dcf9daa6b41fd9501274f0cb2.diff | patch --verbose -p 1
```



## Revert Golang1.25 commit for Windows7/8
this patch file only works on golang1.25.x

that means after golang1.26 release it must be changed

see: https://github.com/MetaCubeX/go/commits/release-branch.go1.25/

revert:
* 693def151adff1af707d82d28f55dba81ceb08e1: "crypto/rand,runtime: switch RtlGenRandom for ProcessPrng"
* 7c1157f9544922e96945196b47b95664b1e39108: "net: remove sysSocket fallback for Windows 7"
* 48042aa09c2f878c4faa576948b07fe625c4707a: "syscall: remove Windows 7 console handle workaround"
* a17d959debdb04cd550016a3501dd09d50cd62e7: "runtime: always use LoadLibraryEx to load system libraries"

sepical fix:
- os.RemoveAll not working on Windows7
```shell
cd $(go env GOROOT)
curl https://github.com/MetaCubeX/go/commit/8cb5472d94c34b88733a81091bd328e70ee565a4.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/6788c4c6f9fafb56729bad6b660f7ee2272d699f.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/a5b2168bb836ed9d6601c626f95e56c07923f906.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/f56f1e23507e646c85243a71bde7b9629b2f970c.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/0a52622d2331ff975fb0442617ec19bc352bb2ed.diff | patch --verbose -p 1
```

## Revert Golang1.24 commit for Windows7/8
this patch file only works on golang1.24.x

that means after golang1.25 release it must be changed

see: https://github.com/MetaCubeX/go/commits/release-branch.go1.24/

revert:
* 693def151adff1af707d82d28f55dba81ceb08e1: "crypto/rand,runtime: switch RtlGenRandom for ProcessPrng"
* 7c1157f9544922e96945196b47b95664b1e39108: "net: remove sysSocket fallback for Windows 7"
* 48042aa09c2f878c4faa576948b07fe625c4707a: "syscall: remove Windows 7 console handle workaround"
* a17d959debdb04cd550016a3501dd09d50cd62e7: "runtime: always use LoadLibraryEx to load system libraries"
```shell
cd $(go env GOROOT)
curl https://github.com/MetaCubeX/go/commit/2a406dc9f1ea7323d6ca9fccb2fe9ddebb6b1cc8.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/7b1fd7d39c6be0185fbe1d929578ab372ac5c632.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/979d6d8bab3823ff572ace26767fd2ce3cf351ae.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/ac3e93c061779dfefc0dd13a5b6e6f764a25621e.diff | patch --verbose -p 1
```

## Revert Golang1.23 commit for Windows7/8
this patch file only works on golang1.23.x

that means after golang1.24 release it must be changed

see: https://github.com/MetaCubeX/go/commits/release-branch.go1.23/

revert:
* 693def151adff1af707d82d28f55dba81ceb08e1: "crypto/rand,runtime: switch RtlGenRandom for ProcessPrng"
* 7c1157f9544922e96945196b47b95664b1e39108: "net: remove sysSocket fallback for Windows 7"
* 48042aa09c2f878c4faa576948b07fe625c4707a: "syscall: remove Windows 7 console handle workaround"
* a17d959debdb04cd550016a3501dd09d50cd62e7: "runtime: always use LoadLibraryEx to load system libraries"
```shell
cd $(go env GOROOT)
curl https://github.com/MetaCubeX/go/commit/9ac42137ef6730e8b7daca016ece831297a1d75b.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/21290de8a4c91408de7c2b5b68757b1e90af49dd.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/6a31d3fa8e47ddabc10bd97bff10d9a85f4cfb76.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/69e2eed6dd0f6d815ebf15797761c13f31213dd6.diff | patch --verbose -p 1
```

## Revert Golang1.22 commit for Windows7/8
this patch file only works on golang1.22.x

that means after golang1.23 release it must be changed

see: https://github.com/MetaCubeX/go/commits/release-branch.go1.22/

revert:
* 693def151adff1af707d82d28f55dba81ceb08e1: "crypto/rand,runtime: switch RtlGenRandom for ProcessPrng"
* 7c1157f9544922e96945196b47b95664b1e39108: "net: remove sysSocket fallback for Windows 7"
* 48042aa09c2f878c4faa576948b07fe625c4707a: "syscall: remove Windows 7 console handle workaround"
* a17d959debdb04cd550016a3501dd09d50cd62e7: "runtime: always use LoadLibraryEx to load system libraries"
```shell
cd $(go env GOROOT)
curl https://github.com/MetaCubeX/go/commit/9779155f18b6556a034f7bb79fb7fb2aad1e26a9.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/ef0606261340e608017860b423ffae5c1ce78239.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/7f83badcb925a7e743188041cb6e561fc9b5b642.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/83ff9782e024cb328b690cbf0da4e7848a327f4f.diff | patch --verbose -p 1
```

## Revert Golang1.21 commit for Windows7/8
modify from https://github.com/restic/restic/issues/4636#issuecomment-1896455557
```shell
cd $(go env GOROOT)
curl https://github.com/golang/go/commit/9e43850a3298a9b8b1162ba0033d4c53f8637571.diff | patch --verbose -R -p 1
```