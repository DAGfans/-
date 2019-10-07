> Source: https://www.cs.huji.ac.il/~yoni_sompo/pubs/15/inclusive_full.pdf

# 3 Security
# 3 安全性

The original security analysis of Satoshi ([10]), as well as analysis done by others [12, 13], has considered the probability of a successful double-spend attack
under the regular non-inclusive scheme. An alternative analysis may instead measure the cost of the attack rather than their success probability (both have
been analyzed in [12]).

Below we prove that the Inclusive version of the protocol is at least as secure as the non-inclusive one, in terms of the probability of successful attacks. In
addition, we show that the cost of an attack under Inclusive can be made high, by properly modifying the acceptance policy.

## 3.1 Acceptance Policy
The recipient of a given transaction observes the network’s published blocks, and needs to decide when to consider the payment “accepted”, that is, when it
is safe to release the goods or services paid for by the transaction. He does so by making sure his transaction is included and confirmed by the main chain, and
calculating the probability that it would be later excluded from it.

Probability of Successful Attacks We now compare the probability of a successful attack under the regular longest-chain protocol to the one under its
Inclusive version. Our method can apply to other main chain rules as well (e.g., GHOST). Recall that under Inclusive the blocks form a DAG, whereas when
Inclusive is not implemented they form a tree (see Sect. 2). Notice that if G(t) is the block DAG at time t, then if the network would have followed the noninclusive setup, its block tree T(t) would be precisely the subgraph of G(t)
obtained by removing all edges in blocks’ reference list apart from the main edges (i.e., the first pointer in every block). For any DAG G let F(G) be its
main chain according to the underlying selection rule F (G can also be a tree).
