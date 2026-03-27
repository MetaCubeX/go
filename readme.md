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
curl https://github.com/MetaCubeX/go/commit/4b29590aa510e05686ea53de16e1e571d22203d8.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/2263b05b2fa6ce228fde1899587baf109f1e2e0a.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/ae41f7abdd5d7b8b51db2c03bf819ac66b8e1eb1.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/ce2e1a3d2c3c0d7277b4102841db1697147d2923.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/4ea1045cf3124221f055dbd2f3d2c9822934f661.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/8149d992682ce76c6af804b507878e19fc966f7b.diff | patch --verbose -p 1
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
curl https://github.com/MetaCubeX/go/commit/6cdeb5754df609758b37af700faab36f0a415c24.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/976d8529fcedabebae5b83e27887e2fbabdad7d2.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/2d6eff769459a1922540978fbd06a2beeee492cd.diff | patch --verbose -p 1
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
curl https://github.com/MetaCubeX/go/commit/f7058fe1ec5898f56434e75bb2c53e1d7735281a.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/f2174047688a295ea6e52c2ab14a8ed19c886b35.diff | patch --verbose -p 1
curl https://github.com/MetaCubeX/go/commit/f852f9a97e6fad6af4a8de3ab9409b532d7dfff9.diff | patch --verbose -p 1
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