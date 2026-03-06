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
* f0894a00f4b756d4b9b4078af2e686b359493583: "os: remove 5ms sleep on Windows in (*Process).Wait"

sepical fix:
- os.RemoveAll not working on Windows7
```shell
cd $(go env GOROOT)
curl https://github.com/MetaCubeX/go/commit/4e83a1914bf2009da8a1f74d3cdd75db812335d4.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/792f314df3838cc01f5934ff3f1b004160cffbb3.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/e794a4ccba66c41ee0cec6a193b57d11f87c4efb.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/bddb37c8868429bb2d8689dc12dd6f317792e8b8.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/bcf122131b9cd23bdc0599e15db2904050cfb5f1.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/030384681641464bf71ed16500075c458363510f.diff | patch --verbose -p 1
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
* f0894a00f4b756d4b9b4078af2e686b359493583: "os: remove 5ms sleep on Windows in (*Process).Wait"

sepical fix:
- os.RemoveAll not working on Windows7
```shell
cd $(go env GOROOT)
curl https://github.com/MetaCubeX/go/commit/466f6c7a29bc098b0d4c987b803c779222894a11.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/1bdabae205052afe1dadb2ad6f1ba612cdbc532a.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/a90777dcf692dd2168577853ba743b4338721b06.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/f6bddda4e8ff58a957462a1a09562924d5f3d05c.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/bed309eff415bcb3c77dd4bc3277b682b89a388d.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/34b899c2fb39b092db4fa67c4417e41dc046be4b.diff | patch --verbose -p 1
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