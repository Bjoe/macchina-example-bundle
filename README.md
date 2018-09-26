# macchina-example-bundle
Example OSGi bundle for macchina (See https://macchina.io/)

**This project is a POC version for macchina**. 

It builds a OSGi bundle with Hunter (See https://docs.hunter.sh/en/latest/) without to checkout macchina.

To build the OSGi bundle do following:

```
$ git clone https://github.com/Bjoe/macchina-example-bundle.git
$ cmake -Hmacchina-example-bundle -Bbuild-macchina-bundle
$ cmake --build build-macchina-bundle
```

This will build a build-macchina-bundle/bundles/com.appinf.osp.samples.servicelistener_1.0.1.bndl bundle and it can be installed into macchina.io.

For more information about macchina see web on web page https://macchina.io/
