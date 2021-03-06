# GUI application to batch rename the fields of a shapefile

## Introduction

This code provides a user interface approach to batch rename the fieldnames (columnnames) of a shapefile. The code uses [tkinter](https://wiki.python.org/moin/TkInter) to provide the user interface and [pandas](https://pypi.python.org/pypi/pandas), [geopandas](https://pypi.python.org/pypi/geopandas) and [fiona](https://pypi.python.org/pypi/Fiona) to perform the conversion.



## Aim

The aim is to rename multiple fields in a shapefile table in one loop (unlike ArcMap, where fields have to be renamed one by one).



## Functionality

### Starting the GUI

The GUI application can be started from the command line as follows:

```python
python batch_rename_fields_shapefile.py
```

This will bring up the following GUI elements, in order:

* A window to select the input shapefile.

* A window to select the textfile which contains the old fieldnames and the new fieldnames.

  > The textfile is structured as follows:
  >
  > - header = None, delimiter = ";", lineterminator = "\n"
  > - old_fieldname_1;new_fieldname_1
  > - old_fieldname_2;new_fieldname_2
  > - ...

* A window to define the output location and the output filename.shp.

The renaming procedure will start automatically after the input are defined.

### Python function

The functionality itself is available as a python function `batch_rename_field_shapefile`, which can be imported as Python module.

When running the function inside Python, make sure the location is added to the PATH in order to enable the import of the function.

Similar to the GUI functionality, the python function `batch_rename_field_shapefile` requires an input file, an info file for the mapping and an output file:

```python
from batch_rename_fields_shapefile import batch_rename_field_shapefile
batch_rename_field_shapefile("my_shapefile.shp", "my_mapping_file.txt", "my_converted_shapfile.py")
```

## Example

To illustrate the functionality, an inline example is provided in the [notebook](https://github.com/inbo/inbo-pyutils/blob/master/gis/batch_rename_fields_shapefile/batch_rename_fields_shapefile.ipynb). Also, an example [textfile](https://github.com/inbo/inbo-pyutils/blob/master/gis/batch_rename_fields_shapefile/mapping_example.txt) is provided.
