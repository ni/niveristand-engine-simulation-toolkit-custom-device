# NI VeriStand Engine Simulation Toolkit Custom Device

The **Engine Simulation Toolkit Custom Device** provides a configuration-based experience for validating engine control units (ECUs).

## LabVIEW Version

LabVIEW 2015 SP1

## Dependencies

Build the packed library in the File Format.lvproj first (Source\File Format Classes)

Requires the [LabVIEW FPGA Advanced Session Resources](https://decibel.ni.com/content/docs/DOC-35574)

OpenG Array Library 4.1.1.14 (Or Later)

OpenG Error Library 4.2.0.23 (Or Later)

OpenG Array Library 4.2.0.21 (Or Later)

NI GXML 1.4.1.7 (Or Later)

LabVIEW .ini token "NI_AppBuilder_SDist_ExcludeEditTime=True"
This prevents the build from including edit time dependencies that are not required at run time for a given target. Without this token, some custom devices will not build.

## Git History & Rebasing Policy
Branch rebasing and other history modifications will be listed here, with several notable exceptions:
- Branches prefixed with `dev/` may be rebased, overwritten, or deleted at any time.
- Pull requests may be squashed on merge.

## License

The NI VeriStand Engine Simulation Toolkit Custom Device is licensed under an MIT-style license (see LICENSE). Other incorporated projects may be licensed under different licenses. All licenses allow for non-commercial and commercial use.