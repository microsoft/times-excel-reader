# Project

**Note: this tool is a work in progress and not yet in a useful state**

This project is an open source tool to convert TIMES model Excel input files to DD format ready for processing by GAMS.  The intention is to make it easier for people to reproduce research results on TIMES models.

The project began as a [Hackathon](https://news.microsoft.com/life/hackathon/) project hence the repo being in the Microsoft organisation, however Microsoft are not funding this work. Further work has been done as part of company Hackathons and the rest in people's own time (both Microsoft employees and not).

TIMES is an energy systems model generator from the International Energy Agency that is used around the world to inform energy policy - https://iea-etsap.org/index.php/etsap-tools/model-generators/times. Detailed documentation is available at https://iea-etsap.org/index.php/documentation

## Overview

The input data is in multiple Excel files and spread across multiple worksheets. Each worksheet can contain any number of data 'tables'. These are annotated by a cell directly above with a tilde and the name of the table e.g. ~FI_T (flexible import table).

Steps:
- Load the input Excel files
- Locate and extract all of the 'tables' into Python objects which include the data as Pandas DataFrames
- Process these tables through a sequence of transforms. These transforms perform a variety of operations from data cleaning to complex operations specific to a single type of table.
- Using the mappings provided in times_mappings.txt, convert the transformed tables into tables ready for the GAMS model to process albeit not yet in DD format. Usually this is a straightforward mapping of table and column names, however it can also select a subset of rows for some tables.
- Write the mapped tables to DD file *(not yet implemented)*

## Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.opensource.microsoft.com.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## Trademarks

This project may contain trademarks or logos for projects, products, or services. Authorized use of Microsoft 
trademarks or logos is subject to and must follow 
[Microsoft's Trademark & Brand Guidelines](https://www.microsoft.com/en-us/legal/intellectualproperty/trademarks/usage/general).
Use of Microsoft trademarks or logos in modified versions of this project must not cause confusion or imply Microsoft sponsorship.
Any use of third-party trademarks or logos are subject to those third-party's policies.
