#!/bin/bash

password="pass1"
name_prefix="user_"
group="users_group"

for i in {1..10}; do
username="${name_prefix}${i}"
useradd -m -d /home/${username} -p $(openssl passwd -1 ${password}) -s /bin/bash ${username}
chown -R ${username} /home/${username}
echo "User ${username} created!"
done
