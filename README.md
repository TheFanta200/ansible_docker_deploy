# Déployer Docker et un conteneur NGINX via Ansible

1. Copier l'intégralité du fichier Ansible dans `/etc/ansible`.

2. Créer le fichier vault permettant de stocker de manière sécurisée tous les comptes utilisés :

    ```bash
    ansible-vault create global_vars/vault.yml
    ```

3. Saisir et modifier les informations suivantes dans le fichier vault :

    ```yaml
    ansible_user: XXXX
    ansible_ssh_pass: XXXX
    ansible_port: 22
    ansible_become: yes
    ansible_become_method: sudo
    ansible_become_user: root
    ansible_become_password: XXXX
    ```

4. Configurer vos hôtes dans le fichier `hosts`.

5. Lancer le playbook :

    ```bash
    ansible-playbook your_playbook.yml 
    ```
