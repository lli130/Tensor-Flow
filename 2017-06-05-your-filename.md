## Create a Class object in Python

### What is Class Object?  
Class object is defined as a logical grouping, consisting of many functions (in this case, called methods).  
It is based on the concept of Object-Oriented Programming. 

### Elements

```
class SparkPlugin(Plugin):
    def save_dataframe(self, df, fileformat):        """ Saves a dataframe with common options """
        coalesce = int(self.args.get("coalesce", 1) or 0)        if coalesce > 0:            df = df.coalesce(coalesce)
        if fileformat == "text":            df.write.text(                self.args["output"],                compression="gzip" if self.args.get("gzip") else "none"            )
        elif fileformat == "json":            df.write.json(                self.args["output"],                compression="gzip" if self.args.get("gzip") else "none"            )
        elif fileformat == "parquet":            df.write.parquet(self.args["output"])
        else:            raise Exception("Unknown format %s" % fileformat)
```
