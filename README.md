# Terraform Stats

[![Test action](https://github.com/JosiahSiegel/terraform-stats/actions/workflows/test_action.yml/badge.svg)](https://github.com/JosiahSiegel/terraform-stats/actions/workflows/test_action.yml)

## Synopsis

Output the following statistics for the Terraform environment:
1. Terraform version
2. Drift count
   * "Drift" refers to changes made outside of Terraform and does not necessary match any resources listed for changes.
3. Resource drifts
4. Change count
   * "Change" refers to change actions that Terraform plans to use to move from the prior state to a new state.
5. Resource changes

## Inputs

```yml
inputs:
  terraform-directory:
    description: Terraform commands will run in this location.
    required: true
    default: "./terraform"
  include-no-op:
    description: "no-op" refers to the before and after Terraform changes are identical as a value will only be known after apply.
    required: true
    default: false
```

## Outputs
```yml
outputs:
  terraform-version:
    description: 'Terraform version'
  drift-count:
    description: 'Count of drifts'
  resource-drifts:
    description: 'JSON output of resource drifts'
  change-count:
    description: 'Count of changes'
  resource-changes:
    description: 'JSON output of resource changes'
```
