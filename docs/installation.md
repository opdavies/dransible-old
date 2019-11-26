# Installation

1. Run `vagrant up` or `vagrant up --provision` if needed, to start Vagrant and provision the virtual machine using the `tools/ansible/provision.yml` playbook. This will set up a LAMP stack with Apache, MySQL, PHP and Composer.

    If you try loading the site at this point you will see a `The requested URL was not found on this server` message as the site has not yet been deployed.

    ![A browser showing a 'Not Found' error](images/before-deploy.png)

1. Run the deploy playbook to deploy the application code to the virtual machine. The Vault password, which is `dransible`, is stored in `tools/ansible/vault-password.txt` as this is an example project.

    ```
    ansible-playbook tools/ansible/deploy.yml \
      -i tools/ansible/hosts.yml \
      --vault-password-file=tools/ansible/vault-password.txt
    ```

1. Load `http://dransible` in a browser, and you should see a Drupal 8 website.

    ![A browser showing the front page of a Drupal website](images/after-deploy.png)
