# Simple python websocket client
# https://github.com/websocket-client/websocket-client
from websocket import create_connection
options = {}
options['origin'] = 'https://exchange.blockchain.com'
url = "wss://ws.blockchain.info/mercury-gateway/v1/ws"
ws = create_connection(url, **options)
msg = '{"token": "{API_SECRET}", "action": "subscribe", "channel": "auth"}'
ws.send(msg)
result =  ws.recv()
print(result)
# { "seqnum":0,
#   "event":"subscribed",
#   "channel":"auth",
#   "readOnly":false }
ws.close()```cpp
std::unique_ptr<vm::Dictionary> get_suspended_addresses(ton::UnixTime now) const;
```

- **Return Type**: `std::unique_ptr<vm::Dictionary>`  
  This indicates the method returns a unique pointer to a `vm::Dictionary`, which likely contains the suspended addresses.

- **Parameter**: `ton::UnixTime now`  
  The method accepts a timestamp (`now`) to determine the state of suspended addresses.

---

### Partial Implementation

```cpp
std::unique_ptr<vm::Dictionary> Config::get_suspended_addresses(ton::UnixTime now) const {
    td::Ref<vm::Cell> param = get_config_param(44);
    ...
}
```

- **Key Points**:
  1. **Fetching Configuration Parameter**:  
     The method retrieves a configuration parameter using `get_config_param(44)`. Here, `44` is likely the identifier for a specific configuration related to suspended addresses.
     
     ```cpp
     td::Ref<vm::Cell> param = get_config_param(44);
     ```

  2. **Return Condition**:  
     Depending on the state of `param` (e.g., null or valid), the method processes the parameter to extract relevant data for suspended addresses. Since the implementation is incomplete (`...`), the processing logic is not visible in the snippet.

  3. **Dictionary Object**:  
     The extracted data is converted into a `vm::Dictionary` object, encapsulated in a `std::unique_ptr`.

---

### Possible Use Case

The `get_suspended_addresses` function could be part of a blockchain configuration system where:
- Certain addresses are temporarily suspended based on specific rules or conditions.
- The function retrieves these addresses for validation, auditing, or other operational purposes.

### Next Steps

To fully understand or utilize this function:
1. **Inspect `get_config_param`**:  
   Review the implementation of `get_config_param` to understand how configuration parameters are retrieved.

2. **Complete the Function Logic**:  
   Identify what happens after fetching `param`. Look for similar methods or documentation to understand how `vm::Dictionary` is constructed.

3. **Explore Config Param `44`**:  
   Investigate what configuration parameter `44` represents. It may be defined elsewhere in the codebase.

Would you like help locating the full implementation or related parts of the code?
