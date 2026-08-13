# Bitcoin Merkle Tree Construction

## Task 2: Merkle Tree Visualization

Four example transaction hashes were used to demonstrate how a Bitcoin Merkle tree is constructed.

### Transaction Hashes

- TxA: `aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa`
- TxB: `bbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbbb`
- TxC: `cccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccc`
- TxD: `dddddddddddddddddddddddddddddddddddddddddddddddddddddddddddddddd`

### Merkle Tree Structure

```text
                         Merkle Root
                              |
                 +------------+------------+
                 |                         |
              Hash(AB)                  Hash(CD)
                 |                         |
            +----+----+              +----+----+
            |         |              |         |
           TxA       TxB            TxC       TxD

Hash(AB)

TxA and TxB are combined and double-hashed using SHA-256.

Result:

499d0d3b39373fb9b7b0f399b7411f7af213d91c32624280e995ae0f8eb776fb

Hash(CD)

TxC and TxD are combined and double-hashed using SHA-256.

Result:

f91baa5f2e2b59bba23970385ccbb4929ef41b2fe48dd86457aedfb3d2ae5e01

Merkle Root

Hash(AB) and Hash(CD) are combined and double-hashed.

Final Merkle Root:

efe8b66f519d513b0fb54df9bfea1da6d31525e04b67a7e85ff5e97090fb02fd

Explanation

A Merkle tree organizes transaction hashes into levels. Pairs of hashes are combined and double-hashed until only one hash remains. The final hash is called the Merkle Root.

The four transaction hashes used in this demonstration are example hashes. The Merkle Root was calculated using Python and double SHA-256 hashing.
