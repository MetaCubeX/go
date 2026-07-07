# MeteCubeX forked Go

using in github action
```yaml
  - name: Set up Go
    uses: actions/setup-go@4a3601121dd01d1626a1e23e37211e3254c1c06c
    with:
      go-download-base-url: 'https://github.com/MetaCubeX/go/releases/download/build'
      go-version: ${{ matrix.go-version }}
```

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
curl https://github.com/MetaCubeX/go/commit/a4ae550aa148b04c9d4890e98bee63aede5c4b53.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/95b851f661584711faa8115b3234a461044f4510.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/b0bf0a863cf218b9bb0d6c013903ab160ae0c39b.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/7c7a2a0d68920f8764d9a3aeae7ad1067a17b3fa.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/ba34356e82f3c12a7303d2231e6ea0e42bbbb3bf.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/472a88edbc2a42feb53fa31d29ab54d33840dca6.diff | patch --verbose -p 1
```

## Revert Golang1.26 commit for macOS
this patch file only works on golang1.26.x

that means after golang1.27 release it must be changed

see: https://github.com/MetaCubeX/go/commits/release-branch.go1.26/

revert:
* 937368f84e545db15d3f39c2b33a267ba8ead4a4: "crypto/x509: change how we retrieve chains on darwin"
* 33d3f603c19f46e6529483230465cd6f420ce23b: "cmd/link/internal/ld: use 12.0.0 OS/SDK versions for macOS linking"
* d90a57ffe8ad8f3cb0137822a768ae48cf80a09d: "cmd/link/internal/ld: unify OS/SDK versions for macOS linking"

```shell
cd $(go env GOROOT)
curl https://github.com/MetaCubeX/go/commit/70cc7249b8cf65e80163d792643de8bd90ad51a6.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/d8f95fa6d13742a90c1810be7cd4b48cdb9cb061.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/fc11427d8d43eb11947d11bf67781a3d9bfa89e8.diff | patch --verbose -p 1
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
curl https://github.com/MetaCubeX/go/commit/da4094da73b3b419e3f347594d805e2831f65667.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/824aa60e77f06dbae86c20a164c78df722eb7047.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/a3b6ba31c8cc67b6d899b978bba7b53e95afc46b.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/edfa8de63435a409a59f60731b66ab5940d6d3a4.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/284f9b24d6284984966a8431e30fdc2583938f96.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/9864798dee8dd47b55d1d5100d2f1b909a2a6e6c.diff | patch --verbose -p 1
```

## Revert Golang1.25 commit for macOS
this patch file only works on golang1.25.x

that means after golang1.26 release it must be changed

see: https://github.com/MetaCubeX/go/commits/release-branch.go1.25/

revert:
* 937368f84e545db15d3f39c2b33a267ba8ead4a4: "crypto/x509: change how we retrieve chains on darwin"
* 33d3f603c19f46e6529483230465cd6f420ce23b: "cmd/link/internal/ld: use 12.0.0 OS/SDK versions for macOS linking"
* d90a57ffe8ad8f3cb0137822a768ae48cf80a09d: "cmd/link/internal/ld: unify OS/SDK versions for macOS linking"

```shell
cd $(go env GOROOT)
curl https://github.com/MetaCubeX/go/commit/ce51192417f9775ce401fed559f533b0e534f04d.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/41e016c2b1e146cf0a5a12d436b95d0d0b61e59e.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/bd25e81d81c109f702b87a4c02a93a2b16ae9b04.diff | patch --verbose -p 1
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