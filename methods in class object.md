## Different methods in Class Object
```
class SparkJob(object):

    name = "Common Search generic job"
    args = None

    def __init__(self):
        pass

    def parse_arguments(self):
        """ Returns the parsed arguments from the command line """

        arg_parser = argparse.ArgumentParser(description=self.name)

        arg_parser.add_argument("--profile", action='store_true',
                                help="Profile Python usage")

        arg_parser.add_argument("--stop_delay", action='store', type=int, default=0,
                                help="Seconds to wait before stopping the spark context")

        self.add_arguments(arg_parser)

        args = arg_parser.parse_args()

        self.validate_arguments(args)

        return args
```

### Static Method  
```
name = "Common Search generic job"
```  
- output:  
Don't have access to self (class object instance)

> SparkJob.name = "Common Search generic job"  

### Inheritance
```
def parse_arguments(self):
```  
- output:  
Returns the parsed arguments from the command line





