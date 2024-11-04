It is a practice based on **automated execution** of certain **processes** after each addition of changes to a software repository. 

A clear example is that when a team member **commits** on version control (git for example), the project is compiled and all its **unit tests and** **_code analysis_** are executed. All this is done automatically.

It is important to implement Continuous Integration to ensure **quality assurance** from early stages of our development.  
Remember, the earlier a bug is found, the **less costly** it will be to fix it.

You will need at a minimum:

- A **source code repository** e.g. Git, SVN, etc.
- A **continuous integration server**to automate all processes, e.g. Jenkins, TeamCity, Travis, etc.
- A **tool** that performs static code analysis.