# Python-related issues and fixes

## Adapting requirements.yml for pip installation

Some repos have library dependencies in the form of requirements.yml, which is commonly used for conda environments. However in some cases, local environments require a pip environment instead. Therefore the below script converts the .yml library dependencies into suitable pip install commands.

```python
import os
import yaml

with open("requirements.yml") as file_handle:
    environment_data = yaml.safe_load(file_handle)

for dependency in environment_data["dependencies"]:
    if isinstance(dependency, dict):
      for lib in dependency['pip']:
        os.system(f"pip install {lib}")
```