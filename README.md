# ansible-openstack-env-template

## workflow
- Create (and edit) a new manifest, using the appropriate sample file:
   ```
   # QA
   cp manifest_templates/qa_manifest.sample envs/manifests/qa01.yml

   # create encrypted file for passwords/keys
   ansible-vault create envs/manifests/qa01.vault.yml
   ```

- Generate Vars
  ```
  ./bin/generate -e qa01
  ```

## usage
```
$ ./bin/generate -h

This script generates the vars needed by ansible-openstack-env-creator to create the templated environment.

USAGE: $0 -e ENV_NAME -t {qa|staging|production}

REQUIRED FLAGS:
  -e      environment

  OPTIONAL FLAGS:
  -t {qa|staging|production} Env type
  -o                         path to output the generated vars (defaults to ./generated_vars)
  -h                         Show this message
```
