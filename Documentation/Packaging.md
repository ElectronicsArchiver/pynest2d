## Creating a new pynest2d Conan package

To create a new pynest2d Conan package such that it can be used in Cura and Uranium, run the following command:

```shell
conan create . pynest2d/<version>@<username>/<channel> --build=missing --update
```

This package will be stored in the local Conan cache (`~/.conan/data` or `C:\Users\username\.conan\data` ) and can be used in downstream
projects, such as Cura and Uranium by adding it as a requirement in the `conanfile.py` or in `conandata.yml`.

Note: Make sure that the used `<version>` is present in the conandata.yml in the pynest2d root

You can also specify the override at the commandline, to use the newly created package, when you execute the `conan install`
command in the root of the consuming project, with:


```shell
conan install . -build=missing --update --require-override=pynest2d/<version>@<username>/<channel>
```