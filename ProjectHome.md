# What it does #
This generic T4 template generates enumerations (C# enum types) out of values defined in a particular database lookup table.
  * generates enumeration values with explicit integer values: they match database values when converting to integers in code;
  * uses Visual Studio's namespace naming convention:  generated enumerations have project's default namespace with any subfolders appended (just like any code file in Visual Studio);
  * adds complete enumeration XML documentation by using additional description table column values; if you don't have these never mind;
  * correctly names the generated file and adds an additional attribute in the code so the generated enum doesn't get scrutinised by code analysis;
  * multi-word lookup table values are correctly concatenated to pascal-cased equivalents (ie. "Multi word value" becomes a "MultiWordValue");
  * enumeration values always start with a letter even when data in data table is different;
  * all enumeration values consist of only letters and numbers, everything else gets cut out;

# How to use #
  1. Save this template in your project or solution folder when you'd like to use it in more than one project and change database connection string in it.
  1. In your project create a new text template item and save it in the folder that will be related to enum's namespace (this is the same as with code files - when you put them in a particular project's subfolder, subfoler names are appended to project's default namespace property). Name the file the same as database table name
  1. add following code to new text template item and save
```
<#@ include file="..\PathToYourT4RelativeToThisTemplate\EnumGenerator.ttinclude" #>
```

That's it.

My [blog post](http://erraticdev.blogspot.com/2011/01/generate-enum-of-database-lookup-table.html) includes the code and also explains all this into great detail.

### Click [this link](http://code.google.com/p/enum-generator-t4/source/browse/) and get the file ###