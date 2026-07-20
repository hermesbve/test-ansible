# test-ansible

Ansible local demo — pure data manipulation (no SSH, no remote hosts).

## Structure

```
vars/               # Per-section variable files
  numbers.yml
  strings.yml
  lists.yml
  dicts.yml

playbooks/          # Sub-playbooks — each independently runnable
  01-numbers.yml    # 25 examples: arithmetic, rounding, comparisons
  02-strings.yml    # 25 examples: case, split/join, regex, base64
  03-lists.yml      # 25 examples: sort, filter, flatten, set ops
  04-dicts.yml      # 25 examples: access, merge, transform, serialize
  main.yml          # Orchestrator — runs all 4, combines output

.github/workflows/ansible-demo.yml
output.lastrun.txt  # Auto-generated on each run
```

Each sub-playbook shows its expected output in the header comments.

## Run

```bash
# A single section:
ansible-playbook playbooks/01-numbers.yml

# All sections (produces output.lastrun.txt):
ansible-playbook playbooks/main.yml
```

## Trigger

- **On push** to `main`
- **Manual** — **Actions → Ansible Demo → Run workflow`
