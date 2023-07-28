# workflow-actions
Holds pipelines to be reused by other repos

## To reuse workflow

```
jobs:
  call-workflow:
    uses: A-I-Team/workflow-actions/.github/workflows/<workflow name>@<branch-name>
    with:
      artifact-name: <artifact-name>
      working-directory: <src code directory name>

```
### Example:
```
jobs:
  call-workflow:
    uses: A-I-Team/workflow-actions/.github/workflows/pipeline.yml@main
    with:
      artifact-name: aa-suggestions
      working-directory: 'aa-suggestions'
```

```
  call-helm-workflow:
    uses: A-I-Team/workflow-actions/.github/workflows/HelmChartPipeline.yaml@AI-508
    with:
      chart-directory: aa-suggestions
    needs: [ call-workflow ]
```