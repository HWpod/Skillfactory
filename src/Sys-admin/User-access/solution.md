# Solution

## Prerequisites

- Switch to root: $ `sudo -i`
- Install ACL: $ `apt-get install acl`

## I. Prepare data directory

- Add a group, create a dir, set access for the group

```bash
# Add a group
USER_GROUP="Employees"
groupadd "$USER_GROUP"

# Create a dir
DATA_DIR="/var/data"
mkdir -p -m 700 "$DATA_DIR"
setfacl -m g:"$USER_GROUP":rx "$DATA_DIR"
setfacl -d -m g:"$USER_GROUP":rx "$DATA_DIR" # set as default
echo -e "\n##### check #####"
ls -ld "$DATA_DIR"
getfacl "$DATA_DIR" 2>/dev/null |grep "$USER_GROUP"

unset USER_GROUP DATA_DIR
```

## II. Add users and user directories

### User `Buh`

Add a user, create a dir, set access for the user

```bash
# Add user
USER="Buh"; USER_GROUP="Employees"
useradd -s /bin/bash "$USER"
usermod -aG "$USER_GROUP" "$USER"

# User dir settings
USER_DIR="Buhgalter"; DATA_DIR="/var/data"
mkdir -p -m 700 "$DATA_DIR/$USER_DIR"
setfacl -m u:"$USER":rwx "$DATA_DIR/$USER_DIR"
setfacl -d -m u:"$USER":rwx "$DATA_DIR/$USER_DIR"
echo -e "\n##### check #####"
id -nG $USER
getfacl "$DATA_DIR/$USER_DIR" 2>/dev/null | awk '/^# file:/ || /^default:user:[^:]+:/'

# User dir settings
USER_DIR="Supply_department"; DATA_DIR="/var/data"
mkdir -p -m 700 "$DATA_DIR/$USER_DIR"
setfacl -m u:"$USER":rwx "$DATA_DIR/$USER_DIR"
setfacl -d -m u:"$USER":rwx "$DATA_DIR/$USER_DIR"
echo -e "\n##### check #####"
id -nG $USER
getfacl "$DATA_DIR/$USER_DIR" 2>/dev/null | awk '/^# file:/ || /^default:user:[^:]+:/'

unset USER USER_DIR USER_GROUP DATA_DIR
```

### User `Hr`

Add a user, create a dir, set access for the user

```bash
# Add user
USER="Hr"; USER_GROUP="Employees"
useradd -s /bin/bash "$USER"
usermod -aG "$USER_GROUP" "$USER"

# User dir settings
USER_DIR="HR"; DATA_DIR="/var/data"
mkdir -p -m 700 "$DATA_DIR/$USER_DIR"
setfacl -m u:"$USER":rwx "$DATA_DIR/$USER_DIR"
setfacl -d -m u:"$USER":rwx "$DATA_DIR/$USER_DIR"
echo -e "\n##### check #####"
id -nG $USER
getfacl "$DATA_DIR/$USER_DIR" 2>/dev/null | awk '/^# file:/ || /^default:user:[^:]+:/'

# User dir settings
USER_DIR="PR"; DATA_DIR="/var/data"
mkdir -p -m 700 "$DATA_DIR/$USER_DIR"
setfacl -m u:"$USER":rwx "$DATA_DIR/$USER_DIR"
setfacl -d -m u:"$USER":rwx "$DATA_DIR/$USER_DIR"
echo -e "\n##### check #####"
id -nG $USER
getfacl "$DATA_DIR/$USER_DIR" 2>/dev/null | awk '/^# file:/ || /^default:user:[^:]+:/'

unset USER USER_DIR USER_GROUP DATA_DIR
```

### User `Pr`

Add a user, create a dir, set access for the user

```bash
# Add user
USER="Pr"; USER_GROUP="Employees"
useradd -s /bin/bash "$USER"
usermod -aG "$USER_GROUP" "$USER"

# User dir settings
USER_DIR="PR";DATA_DIR="/var/data"
mkdir -p -m 700 "$DATA_DIR/$USER_DIR"
setfacl -m u:"$USER":rwx "$DATA_DIR/$USER_DIR"
setfacl -d -m u:"$USER":rwx "$DATA_DIR/$USER_DIR"
echo -e "\n##### check #####"
id -nG $USER
getfacl "$DATA_DIR/$USER_DIR" 2>/dev/null | awk '/^# file:/ || /^default:user:[^:]+:/'

# User dir settings
USER_DIR="Buhgalter"; DATA_DIR="/var/data"
mkdir -p -m 700 "$DATA_DIR/$USER_DIR"
setfacl -m u:"$USER":rwx "$DATA_DIR/$USER_DIR"
setfacl -d -m u:"$USER":rwx "$DATA_DIR/$USER_DIR"
echo -e "\n##### check #####"
id -nG $USER
getfacl "$DATA_DIR/$USER_DIR" 2>/dev/null | awk '/^# file:/ || /^default:user:[^:]+:/'

unset USER USER_DIR USER_GROUP DATA_DIR
```

### User `Sup`

Add a user, create a dir, set access for the user

```bash
# Add user
USER="Sup"; USER_GROUP="Employees"
useradd -s /bin/bash "$USER"
usermod -aG "$USER_GROUP" "$USER"

# User dir settings
USER_DIR="Supply_department"; DATA_DIR="/var/data"
mkdir -p -m 700 "$DATA_DIR/$USER_DIR"
setfacl -m u:"$USER":rwx "$DATA_DIR/$USER_DIR"
setfacl -d -m u:"$USER":rwx "$DATA_DIR/$USER_DIR"
echo -e "\n##### check #####"
id -nG $USER
getfacl "$DATA_DIR/$USER_DIR" 2>/dev/null | awk '/^# file:/ || /^default:user:[^:]+:/'

# User dir settings
USER_DIR="Buhgalter"; DATA_DIR="/var/data"
mkdir -p -m 700 "$DATA_DIR/$USER_DIR"
setfacl -m u:"$USER":r-x "$DATA_DIR/$USER_DIR"
setfacl -d -m u:"$USER":r-x "$DATA_DIR/$USER_DIR"
echo -e "\n##### check #####"
id -nG $USER
getfacl "$DATA_DIR/$USER_DIR" 2>/dev/null | awk '/^# file:/ || /^default:user:[^:]+:/'

unset USER USER_DIR USER_GROUP DATA_DIR
```

### User `HD_1`

Add a user, create a dir, set access

```bash
# Add user
USER="HD_1"; USER_GROUP="Employees"
useradd -s /bin/bash "$USER"
usermod -aG "$USER_GROUP" "$USER"

# User dir settings
USER_DIR="PR"; DATA_DIR="/var/data"
mkdir -p -m 700 "$DATA_DIR/$USER_DIR"
setfacl -m u:"$USER":rwx "$DATA_DIR/$USER_DIR"
setfacl -d -m u:"$USER":rwx "$DATA_DIR/$USER_DIR"
echo -e "\n##### check #####"
id -nG $USER
getfacl "$DATA_DIR/$USER_DIR" 2>/dev/null | awk '/^# file:/ || /^default:user:[^:]+:/'

# User dir settings
USER_DIR="Supply_department"; DATA_DIR="/var/data"
mkdir -p -m 700 "$DATA_DIR/$USER_DIR"
setfacl -m u:"$USER":rwx "$DATA_DIR/$USER_DIR"
setfacl -d -m u:"$USER":rwx "$DATA_DIR/$USER_DIR"
echo -e "\n##### check #####"
id -nG $USER
getfacl "$DATA_DIR/$USER_DIR" 2>/dev/null | awk '/^# file:/ || /^default:user:[^:]+:/'

# User dir settings
USER_DIR="Buhgalter"; DATA_DIR="/var/data"
mkdir -p -m 700 "$DATA_DIR/$USER_DIR"
setfacl -m u:"$USER":rwx "$DATA_DIR/$USER_DIR"
setfacl -d -m u:"$USER":rwx "$DATA_DIR/$USER_DIR"
echo -e "\n##### check #####"
id -nG $USER
getfacl "$DATA_DIR/$USER_DIR" 2>/dev/null | awk '/^# file:/ || /^default:user:[^:]+:/'

# User dir settings
USER_DIR="HR"; DATA_DIR="/var/data"
mkdir -p -m 700 "$DATA_DIR/$USER_DIR"
setfacl -m u:"$USER":r-x "$DATA_DIR/$USER_DIR"
setfacl -d -m u:"$USER":r-x "$DATA_DIR/$USER_DIR"
echo -e "\n##### check #####"
id -nG $USER
getfacl "$DATA_DIR/$USER_DIR" 2>/dev/null | awk '/^# file:/ || /^default:user:[^:]+:/'

unset USER USER_DIR USER_GROUP DATA_DIR
```

### III. Create files

```bash
DATA_DIR="/var/data"

touch $DATA_DIR/Buhgalter/file1
touch $DATA_DIR/HR/file1
touch $DATA_DIR/PR/file1
touch $DATA_DIR/Supply_department/{file1,file2}

echo -e "\n##### check #####"
getfacl -R $DATA_DIR/*/* |grep -E 'file:|user:([^:]|group:[^:])'

unset USER USER_DIR USER_GROUP DATA_DIR
```
