#### Make

```
git clone https://github.com/xiph/theora.git
cd ./theora
git checkout theora-multithread
# git checkout 02174f9
```
#### Build

```
cd ./macosx
xcodebuild -scheme "libtheoradec (static)" -sdk macosx -arch arm64 -ONLY_ACTIVE_ARCH=YES -configuration Release HEADER_SEARCH_PATHS=../../../libogg-xcframework/ogg/include -SKIP_INSTALL=NO
xcodebuild -scheme "libtheoradec (static)" -sdk iphoneos -arch arm64 -ONLY_ACTIVE_ARCH=YES -configuration Release HEADER_SEARCH_PATHS=../../../libogg-xcframework/ogg/include -SKIP_INSTALL=NO
xcodebuild -scheme "libtheoradec (static)" -sdk iphonesimulator -arch arm64 -ONLY_ACTIVE_ARCH=YES -configuration Release HEADER_SEARCH_PATHS=../../../libogg-xcframework/ogg/include -SKIP_INSTALL=NO
```

#### Copy

```
cp ./build/Release/libtheoradec.a ../../libtheoradec.xcframework/macos-arm64/libtheoradec.a
cp ./build/Release-iphoneos/libtheoradec.a ../../libtheoradec.xcframework/ios-arm64/libtheoradec.a
cp ./build/Release-iphonesimulator/libtheoradec.a ../../libtheoradec.xcframework/ios-arm64-simulator/libtheoradec.a
```