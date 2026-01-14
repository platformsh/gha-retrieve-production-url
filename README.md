# Platform.sh Retrieve Project Production URL

Retrieves the production URL of the integrated Platform.sh project that is connected to a repository 

## Inputs
* `platformsh_token` **REQUIRED** - A Platform.sh API Token.
* `project_id` - **REQUIRED** The Platform.sh Project ID of the associated project.
* `provider` - The CLI tool to use. Valid options: `upsun` and `platform` (Upsun Fixed). Defaults to `platform`

## Outputs
* `production_url` - production URL of the integrated Platform.sh project. 
## Example Usage
```yaml
    - name: 'Get our Production URL'
      id: get-production-url
      uses: platformsh/gha-retrieve-production-url@main
      with:
        platformsh_token: ${{ secrets.PSH_TOKEN }}
        project_id: ${{ vars.PROJECT_ID }}

    - name: "Use our Production URL"
      run: |
        echo "::notice::Our production URL is ${{ steps.get-get-production-url.output.production_url }}"
```

