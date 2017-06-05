## Create a Class object in Python

### What is Class Object?  
Class object is defined as a logical grouping, consisting of many functions (in this case, called methods).  
It is based on the concept of Object-Oriented Programming. 

### Elements

```
class SparkPlugin(Plugin):
	def __init__(self, plugin_name, options):
        """Return a SparkPlugin object whose name is *plugin_name* and contains options."""
        self.plugin_name = name
        self.options = options


    def save_dataframe(self, df, fileformat):
        """ Saves a dataframe with common options """

        coalesce = int(self.args.get("coalesce", 1) or 0)
        if coalesce > 0:
            df = df.coalesce(coalesce)

        if fileformat == "text":
            df.write.text(
                self.args["output"],
                compression="gzip" if self.args.get("gzip") else "none"
            )

        elif fileformat == "json":
            df.write.json(
                self.args["output"],
                compression="gzip" if self.args.get("gzip") else "none"
            )

        elif fileformat == "parquet":
            df.write.parquet(self.args["output"])

        else:
            raise Exception("Unknown format %s" % fileformat)
```  
1. class object named SparkPlugin  
- input:  
after '_init_', it can create an initialized object
> eg. plugin1 = SparkPlugin("plugin1_test", options= None)  

- output:  
return a SparkPlugin object containing plugin_name and options (two attributes)

2. method named save_dataframe(self, df, fileformat)  
- self oject  
an instance of SparkPlugin object

- input  
```
SparkPlugin.save_dataframe(plugin1, df1, "JSON")  
```
is equal to  
```
plugin1.save_dataframe(df1, "JSON")
```  
- output  
an updated SparkPlugin instance after implementing save_dataframe method.

