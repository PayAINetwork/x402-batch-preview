# PayAI Solana batch-settlement preview artifacts

This public repository hosts PayAI's pinned preview builds of `@x402/core` and `@x402/svm` for Solana batch settlement. Install the two tarballs together from the [PayAI-owned preview release](https://github.com/PayAINetwork/x402-batch-preview/releases/tag/payai-batch-preview-20260913):

```sh
npm install \
  https://github.com/PayAINetwork/x402-batch-preview/releases/download/payai-batch-preview-20260913/x402-core-2.24.0-af8e7235.tgz \
  https://github.com/PayAINetwork/x402-batch-preview/releases/download/payai-batch-preview-20260913/x402-svm-2.24.0-e8ef0552-recovery.tgz \
  @solana/kit@^5.5.1
```

The release files are byte-for-byte copies of the original 2026-09-13 preview, not a rebuild. Their SHA-256 hashes are:

| Asset | SHA-256 |
| --- | --- |
| `x402-core-2.24.0-af8e7235.tgz` | `6e7d2197e7cb97147921ad8777f817ff2eeb0fbe7797dbeacb3816cd64deaf0d` |
| `x402-svm-2.24.0-e8ef0552-recovery.tgz` | `e3c229ac72cce15e7b6f9c34e1ab8324329df65b3377fd890eedf9926c320977` |

The `SHA256SUMS`, smoke-test script, and smoke-test guide are mirrored unchanged too. The package source revisions are [core `af8e7235`](https://github.com/notorious-d-e-v/x402/commit/af8e7235) and [SVM `e8ef0552`](https://github.com/notorious-d-e-v/x402/commit/e8ef05529663a86b0f61c082a9b25d9762e0fb14). The release tag in this repository identifies the artifact mirror; it is not the SDK source commit.

These packages retain the `@x402/*` names and are a PayAI preview, not an official x402 or Solana Foundation release. Org-owned GitHub hosting removes the personal-release availability dependency; it does not provide an npm semver line or remove downstream package overrides. Keep lockfiles pinned and follow the [merchant integration guide](https://docs.payai.network/x402/servers/batch-settlement) for the active policy and recovery requirements.

The SDK source is licensed under Apache-2.0; see [LICENSE](LICENSE) and [NOTICE](NOTICE).
