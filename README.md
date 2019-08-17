# How To Reproduce

1. Clone this repo, you shouldn have no Pods folder in your local repo for it's ignored by git
2. Do `pod install` and nothing change (or may only change task hash ID of `[CP] Copy Pods Resources`). Compile project and all goes well.
3. Do `pod install`  again, and new changes appear on `BuildFailExample.xcodeproj/project.pbxproj`. ` [CP] Copy Pods Resources` build phase script is removed and project will fail to build because `Firebase.h` can not be found in its modulemap.
4. This is because that Original Firebase header in `Pods/Firebase/CoreOnly/Source/Firebase.h` is removed during second `pod install`
5. Clear all Pods folder by `rm -rf Pods` , and then you go back to step 1.

