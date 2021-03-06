gNMI tool
----

gnmi-cli.py is a script for user to send gNMI **Get**, **Set** request and **Subscribe**.

## Usage

```
usage: gnmi-cli.py [-h] [--grpc-addr GRPC_ADDR] [--bool-val BOOL_VAL]
                   [--int-val INT_VAL] [--uint-val UINT_VAL]
                   [--string-val STRING_VAL] [--float-val FLOAT_VAL]
                   {get,set,sub} path

Test gNMI subscription

positional arguments:
  {get,set,sub}         gNMI command
  path                  gNMI Path

optional arguments:
  -h, --help            show this help message and exit
  --grpc-addr GRPC_ADDR
                        gNMI server address
  --bool-val BOOL_VAL   [SetRequest only] Set boolean value
  --int-val INT_VAL     [SetRequest only] Set int value
  --uint-val UINT_VAL   [SetRequest only] Set uint value
  --string-val STRING_VAL
                        [SetRequest only] Set string value
  --float-val FLOAT_VAL
                        [SetRequest only] Set float value
```

## Examples

```
# To get port index
./gnmi-cli.py get /interfaces/interface[name=1/1/1]/state/ifindex

# To set port health indicator
./gnmi-cli.py set /interfaces/interface[name=1/1/1]/config/health-indicator --string-val GOOD

# To subscribe port operation status
./gnmi-cli.py sub /interfaces/interface[name=1/1/1]/state/oper-status
```
