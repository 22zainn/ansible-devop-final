source ~/ansible-venv/bin/activate
ansible-vault create group_vars/sonar/vault.yml
sonar_db_password: "REPLACE_WITH_A_STRONG_PASSWORD"
ansible-playbook playbooks/setup.yml --ask-vault-pass
ansible-playbook playbooks/setup-https.yml  --ask-vault-pass
ansible-playbook playbooks/destroy.yml
deactivate