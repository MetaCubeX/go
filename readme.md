# MeteCubeX forked Go

using in github action
```yaml
  - name: Set up Go
    uses: actions/setup-go@4a3601121dd01d1626a1e23e37211e3254c1c06c
    with:
      go-download-base-url: 'https://github.com/MetaCubeX/go/releases/download/build'
      go-version: ${{ matrix.go-version }}
```

## Revert Golang1.27 commit for Windows7/8
this patch file only works on golang1.27.x

that means after golang1.28 release it must be changed

see: https://github.com/MetaCubeX/go/commits/release-branch.go1.27/

revert:
* 341b5e2c0261cc059b157f1c7a2a2c4d1f417f0d: "cmd/link: raise minimum windows version to 10"
* 693def151adff1af707d82d28f55dba81ceb08e1: "crypto/rand,runtime: switch RtlGenRandom for ProcessPrng"
* 7c1157f9544922e96945196b47b95664b1e39108: "net: remove sysSocket fallback for Windows 7"
* 48042aa09c2f878c4faa576948b07fe625c4707a: "syscall: remove Windows 7 console handle workaround"
* a17d959debdb04cd550016a3501dd09d50cd62e7: "runtime: always use LoadLibraryEx to load system libraries"
* f0894a00f4b756d4b9b4078af2e686b359493583: "os: remove 5ms sleep on Windows in (*Process).Wait"

sepical fix:
- os.RemoveAll not working on Windows7
```shell
cd $(go env GOROOT)
curl https://github.com/MetaCubeX/go/commit/5bea096a8d38bcc2f7b29a423a2d7a677e7257b4.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/2fd9d96c8897586872cf00e335dad7d0e2d32601.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/51cbeef333241001a1106fbeeb7c7ef80054dac2.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/4fd81ff5c9844620e836e8d2052e082ac26484f0.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/2924464d68627505f876d4d275bf8432dbf81da5.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/5c36850df445d11d557c3d995e15a3ac159749ea.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/51c81072acbed32e4331026bc6ca308a3a495039.diff | patch --verbose -p 1
```

## Revert Golang1.27 commit for macOS
this patch file only works on golang1.27.x

that means after golang1.28 release it must be changed

see: https://github.com/MetaCubeX/go/commits/release-branch.go1.27/

revert:
* 937368f84e545db15d3f39c2b33a267ba8ead4a4: "crypto/x509: change how we retrieve chains on darwin"
* 6614616b7576a8011053c4b50fbb5e64d469837b: "cmd/link: use 13.0.0 OS version for macOS linking"
* 3d7681ebab6fca8f859d8fc7d6c02c90ef379c05: "cmd/link: fix macOS 13 build"
* 23fde5c48c9bacb0ec8f5e21cc72191c64364ce1: "cmd/link: add -macos and -macsdk flags to set LC_BUILD_VERSION"
* 33d3f603c19f46e6529483230465cd6f420ce23b: "cmd/link/internal/ld: use 12.0.0 OS/SDK versions for macOS linking"
* d90a57ffe8ad8f3cb0137822a768ae48cf80a09d: "cmd/link/internal/ld: unify OS/SDK versions for macOS linking"

```shell
cd $(go env GOROOT)
curl https://github.com/MetaCubeX/go/commit/e515bdaa0a718950bfe427cc8488d1872b25240d.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/05330c9934b907f0fb7ff51c90d03cadb45c8246.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/79be7711a9490392bfa109a378ba287827c624e3.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/64f733bb77ba6369206d214633e18666007f36d1.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/6f035b951513a7076b30d446a76e0de8e5a962cb.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/c130b84646b4e4c5c2833371a0ad0bc3b3117b10.diff | patch --verbose -p 1
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
curl https://github.com/MetaCubeX/go/commit/19633fd8b337ea581aef3523feedb495242a47a1.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/b4ca091bbdaef511a70fcf47f456d4a310a9b06c.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/c436b1f2a32b9cf3a761ba3066a5e3942724dc71.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/bd0c2fb36bca4b079e179c9af48e4b9cdc097531.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/9301b33458084af5c824c0758bc0aa3fc69a1ce8.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/ec897a1861d1060f5818c70dddbc86a6223fa5f4.diff | patch --verbose -p 1
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
curl https://github.com/MetaCubeX/go/commit/099e79441346a5ac847378181a029e70708249ac.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/c869203fca5c5747b5f6d6f2d71a62c3087677d8.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/4618a06c17a409f2ae16134c70e563867a630d69.diff | patch --verbose -p 1
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
curl https://github.com/MetaCubeX/go/commit/8d9e3f1d7d91dbd2eee13595ce4a40cd8be503d4.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/7b1bc112a061417faeb95b2cff871c32612255fe.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/e7dfa12a37b951470e9c30ff20824ee5828b8783.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/7b6aad8f5ee4efaba7a9cc6e88fb69b7dc16c42d.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/060eda91a4318038ff182ae45b5706a86c02d75a.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/9f2e6c6ddd9f63a8648673212335c332742be057.diff | patch --verbose -p 1
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
curl https://github.com/MetaCubeX/go/commit/42d7ff5bf3cfc00bc51b75758280fe2ce4fed859.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/9182fc66edebd7df0bf98292f091f20addac8347.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/832d2591087f3ffa406dbe0d63aec2ef720c3a6d.diff | patch --verbose -p 1
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
