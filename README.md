# Configuration of MACOSX


I had to change the following file on Sierra (MacOs 10.12):
Some basic Git commands are:
```
sudo chmod a+w /Library/Developer/CommandLineTools/SDKs/MacOSX.sdk/usr/include/CommonCrypto/CommonRandom.h
vi /Library/Developer/CommandLineTools/SDKs/MacOSX.sdk/usr/include/CommonCrypto/CommonRandom.h
```

I've added the following line before the `typedef` statement:
```
#include "CommonCrypto/CommonCryptoError.h"
```
And also followed the advice of @Hulkur - run command:
```
brew edit openssl
```
and added
```
-I/Library/Developer/CommandLineTools/SDKs/MacOSX.sdk/usr/include
```
to `args` array in `configure_args`.
