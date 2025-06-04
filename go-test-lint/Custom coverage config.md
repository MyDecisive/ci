# How consumers specify their own config:
In the consuming repository's workflow:
```yaml
jobs:
  test:
    steps:
      - uses: decisiveai/ci/go-test-lint@main
        with:
          config-path: ./.github/.testcoverage.yml  # Custom config
```

Or if they want to use a different location:
```yaml
  - uses: decisiveai/ci/go-test-lint@main
    with:
      config-path: ./custom-coverage.yml
```

If you don't specify config-path at all, it uses the default config from the action repo.

> Consumer provides config-path input → uses their custom config
> 
> No config-path provided → uses your default config from github.action_path

This gives us org-wide standards by default while allowing per-repo customization when 
needed.