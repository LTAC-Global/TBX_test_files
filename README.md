# These are test files 
These files are intended to show how to validate TBX files from different dialects. At each level, there is a file that is valid and a file that should be rejected by that dialect's schema. The demonstrated dialects are TBX-Core, TBX-Min, and TBX-Basic, which are detailed [on the TBX website](https://www.tbxinfo.net/tbx-modules/).

# How to validate with oXygen
First, **open the TBX file** to validate in oXygen.

Then, **associate the TBX file** with applicable schemas against which it will be validated. For all dialects you will need to validate against the **TBX core structure**. Insert the following line of code XML at the top of your TBX file, above the opening tag of the <tbx> element; replace `PATH` with the relative filepath from the TBX file to wherever you have placed the `core_schema.rng` file:

`<?xml-model href="PATH/core_schema.rng" type="application/xml" schematypens="http://relaxng.org/ns/structure/1.0"?>`

For TBX-Min, TBX-Basic, or any other dialect, there are **Schematron rules** to associate in addition to the TBX core structure. Add the following XML just after the line for the core structure, again replacing `PATH` with the relative filepath from the TBX file to the Schematron file (for TBX-Min and TBX-Basic, this would be min_schema.sch and basic_schema.sch, respectively):

`<?xml-model href="PATH" type="application/xml" schematypens="http://purl.oclc.org/dsdl/schematron"?>`

Finally, **validate the TBX file** by clicking the icon on the top toolbar which shows a page with a big red checkmark on it. Any errors will be displayed at the bottom of the screen. Success will yield a green square and a success message.
