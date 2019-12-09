# stacks/

The stacks/ directory contains one or more stack definitions. A stack definition consists of a 

|  |  | Optional |
| :--- | :--- | :--- |
| stack.yaml | Defines and configures the slices in the story | No  |
| templates.html | Defines custom html templates to use in slices. | Yes, can be omitted if no custom templates are used. |
| dataservices.py | Contains one or more data services that provide data to slices. The name of this file can be any valid python file name. | Yes, can be omitted if **only** fixture data is used for slices  |
| fixtures/ | A directory containing data service fixtures to use for slices. Fixtures are json files that provide unchanging Juicebox responses | Yes, can be omitted if **no fixture data** is used. |
| help/ | A directory containing tour definition yaml files.  | Yes, can be omitted of no tours are used in the slice. |

Each stack tells a self-contained data story. When the user reaches the end of the story, a Story Chooser allows them to decide what they want to see next.

Keep going to the next page to 

