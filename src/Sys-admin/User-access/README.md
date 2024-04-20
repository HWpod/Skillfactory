# Task - User Access

## Linux System

### Objective

Create directories in `/var/data` and users, assigning specific access rights as detailed below.

#### User: `user_name`

- *Type* access: 'directory_name'

___

### Details

#### User: `Buh`

- *full*: 'Buhgalter'
- *full*: 'Supply_department'

#### User `Hr`

- *full*: 'HR'
- *full* 'PR'

#### User `Pr`

- *full*: 'PR'
- *full*: 'Buhgalter'

#### User `Sup`

- *full*: 'Supply_department'
- *read*: 'Buhgalter'

#### User `HD_1`

- *full*: 'PR'
- *full*: 'Supply_department'
- *full*: 'Buhgalter'
- *read*: 'HR'
