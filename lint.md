## For Linting Issues ( File is not `gci`-ed with --skip-generated -s standard -s default (gci) )

Step 1. `curl -sSfL https://raw.githubusercontent.com/golangci/golangci-lint/master/install.sh | sh -s -- -b $(go env GOPATH)/bin v1.57.2`

Step 2. `/root/go/bin/golangci-lint run [FILE_PATH]`
