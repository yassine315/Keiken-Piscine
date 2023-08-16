# Understand permissions & Access
## How is permission granted to delete a file? 
If a user has write and execute permissions on a directory, the user can delete files within that directory regardless of whether the user owns the file or not. If the user lacks either permission, the user won't be able to delete files within that directory, regardless of file-specific permissions.
## Create a file that your colleague can edit but not delete and another he can delete but not edit
1. user 1
    ```bash
    touch first && chmod o+trw first
    ```
2. user 2
    ```bash
    touch second && chmod o-tw
    ```
## Does it make sense to be able to assign such rights
user is granted the ability to edit a file, they can essentially clear its content, rendering it functionally useless except in cases where the file's mere existence holds significance, such as for a program that requires the presence of the file, The purpose of restricting write access is typically to prevent the introduction of malicious code that could potentially be executed using that file. Allowing deletion while limiting write access could lead to inconsistencies in security considerations.