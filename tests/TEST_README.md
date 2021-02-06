Tests go in this folder. Use the [pytest-workflow](https://pytest-workflow.readthedocs.io/en/stable/) syntax. 

## Example

For example, let's say you have a `hello.wdl` workflow at the project root:

```wdl
task hello {
  command {
    echo "Hello, world!"
  }
  output {
    File hello_out = stdout()
  }
  runtime {
    docker: "ubuntu:latest"
  }
}

workflow hello_workflow {
  call hello
}
```

Then you can create a test for it that looks like this:
```yaml
- name: hello_test
  command: miniwdl run -d test-output/. hello.wdl
  files:
    - path: test-output/out/hello.hello_out/stdout.txt
      contains:
        - "Hello, world!"
```

The tests are run by CI, or you can test locally with this command:
`pipenv run python -m pytest`
