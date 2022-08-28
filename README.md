This tutorial shows how to implement python linting by GitHub workflows. I have used Pylint frame work to lint all the python files and display the score of each python file. If python file has a score less than 6.0 the workflow fails. This workflow is capable of linting python files which are present in the subdirectory as well. 

- name: Lints each python file and fails if pylint score is less than 6.0
        run: |
              for file in $(find -name '*.py')
              do
                pylint --disable=E0401,W0611 "$file" --fail-under=6.0;    
              done