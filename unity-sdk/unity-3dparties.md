---
uid: unity-3dparties
---

# Trivver 3rd party libraries

No one likes to add additional dependencies to his project. We are trying to minimize dependencies list but still have to use several 3rd party libraries.

- [MsgPack (ver 0.8.0)](http://msgpack.org/) - for sending statistical data
- [Newtonsoft.Json (ver 9.0.0)](http://www.newtonsoft.com/json) - native Unity Json Serialization engine is not suitable for us.
- [SharpZipLib (ver 0.86.0.518)](https://github.com/icsharpcode/SharpZipLib) - for decompression of models.

## Reference conflict

It is possible that your game will use same libraries. Two options here:

1. Use vendors shipped with Trivver.
2. Use own versions and remove Trivver vendors.

In case you choose option 2 you need to place assemblies to Plugins folder, e.g. `Assets/Plugins/MyVendors`,
 because Trivver has scripts which are compiled in first pass assembly. Trivver uses small subset of functionality of 
 these libraries, and there is high probability that everything will be fine, but we can't guarantee that, especially if versions are dramatically different.
