[![Python package](https://github.com/SermetPekin/verser-repo/actions/workflows/python-package.yml/badge.svg)](https://github.com/SermetPekin/verser-repo/actions/workflows/python-package.yml)
[![Downloads](https://pepy.tech/badge/verser/week)](https://pepy.tech/project/verser)
[![Python 3.8](https://img.shields.io/badge/python-3.8-blue.svg)](https://www.python.org/downloads/release/python-380/)
[![Python 3.9](https://img.shields.io/badge/python-3.9-blue.svg)](https://www.python.org/downloads/release/python-390/)
[![Python 3.10](https://img.shields.io/badge/python-3.10-blue.svg)](https://www.python.org/downloads/release/python-310/)


# compat

    from compat import Project, get_next_version, get_current_version

### checks if user's python version is compatible with your project

    def check_compat(
            min_version: str,
            max_version: str,
            min_msg: t.Union[str, t.Callable] = default_min_msg,
            max_msg: t.Union[str, t.Callable] = default_max_msg,
            compatible_msg: t.Union[str, t.Callable] = default_compat_msg,
            verbose: bool = True,
            mock_sys_version: t.Union[str, bool] = False, # for test purposes
    
    ):


###  Use case 1 : main file on your project to continue or stop running 
>>  you may use it on the main file of your project 
>> and create a conditional and decide what to do next 

    if check_compat(
            min_version="3.7",
            max_version="3.11",
            min_msg="Your version is less than minimum.",
            verbose=True,

        ) is False : 
            sys.exit(0) # return # or just exit
    # if user's python has a version of lets say 3.4 this will print your customized message and exit.


>> and create a conditional and decide what to do next 

    if check_compat(
            min_version="3.7",
            max_version="3.10",
            min_msg="Your version is less than minimum.",
            max_msg="Your version is greater than the minimum.",
            verbose=True,

        ) is False : 
            pass   
    # if user's machine has a python with version of 
    # lets say 3.4 this will print your customized message and continue .

