# Ross Dashboard GraphQL Proxy Debugging

This repo provides:
- Example OGScript for sending GraphQL mutations/queries from Ross Dashboard
- How to use [mitmproxy](https://mitmproxy.org/) as a local debugging proxy for GraphQL APIs

## Prerequisites

- [mitmproxy](https://mitmproxy.org/) installed (`pip install mitmproxy`)
- Access to your Ross Dashboard environment

## Usage

1. **Run mitmproxy in reverse proxy mode:**

    ```sh
    mitmproxy --mode reverse:https://<YOUR_GRAPHQL_SERVER>:443
    ```

2. **Paste the OGScript into your Ross Dashboard script editor:**

    - Update the `Authorization` and `deviceId` placeholders as required

3. **Inspect requests/responses in mitmproxy for debugging**

## Example OGScript

See [`ogscript/sample_graphql_mutation.ogscript`](ogscript/sample_graphql_mutation.ogscript) for a sanitized template.

## Example mitmproxy Script

If you need to inject headers via mitmproxy, see [`mitmproxy/add_auth.py`](mitmproxy/add_auth.py).

