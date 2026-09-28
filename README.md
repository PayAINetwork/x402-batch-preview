# PayAI Solana batch-settlement preview artifacts

This public repository hosts PayAI's pinned preview builds of `@x402/core` and `@x402/svm` for Solana batch settlement. Install the two tarballs together from the published [PayAI-owned prerelease](https://github.com/PayAINetwork/x402-batch-preview/releases/tag/payai-batch-preview-20260928-upstream):

```sh
npm install \
  https://github.com/PayAINetwork/x402-batch-preview/releases/download/payai-batch-preview-20260928-upstream/x402-core-2.27.0-c84154b5.tgz \
  https://github.com/PayAINetwork/x402-batch-preview/releases/download/payai-batch-preview-20260928-upstream/x402-svm-2.27.0-3646356c1-payai5.tgz \
  @solana/kit@^5.5.1
```

The package assets, source revisions, and SHA-256 hashes are:

| Asset | Source revision | SHA-256 |
| --- | --- | --- |
| `x402-core-2.27.0-c84154b5.tgz` | x402 Foundation [`c84154b5d6a31d77fd5b9dbb01213053fd9cb9eb`](https://github.com/x402-foundation/x402/commit/c84154b5d6a31d77fd5b9dbb01213053fd9cb9eb) | `cc5dda38a1697546e163d41601aa92765b826ff4d74f952f82757090f740b99b` |
| `x402-svm-2.27.0-3646356c1-payai5.tgz` | PayAI [`3646356c12080b9dd17774a8e444c67b3e4be2d8`](https://github.com/PayAINetwork/x402/commit/3646356c12080b9dd17774a8e444c67b3e4be2d8) | `68f8a6bd9ec19ef88cf1b3679f9c8cff479072fd47f84f848e35ab2e2f121351` |

The core tree is unchanged through the SVM revision. The SVM package includes the merged upstream batch-settlement implementation and bounded channel-PDA cache, plus PayAI's recovery and cleanup hooks, server-operation replay, server-mode payer forced-close compatibility, deposit lifecycle confirmation, and seal-payout accounting callback. Its packaged manifest replaces the monorepo's `workspace:~` core dependency with the publishable range `~2.27.0`; its compiled `dist` is otherwise byte-for-byte identical to that source build. Use the release's `SHA256SUMS` to verify every uploaded file. The release tag identifies this artifact mirror, not an SDK source revision.

The [x402 Foundation repository](https://github.com/x402-foundation/x402) and its official npm packages remain the source of truth. These tarballs retain the `@x402/*` names but are PayAI prerelease artifacts, not an official x402 Foundation release. Keep both asset URLs, lockfile integrity values, and hashes pinned together. When upstream publishes compatible official `@x402/core` and `@x402/svm` versions, replace both tarball URLs with those npm versions, regenerate the lockfile, remove preview-specific package overrides, and run the batch-settlement integration and recovery tests before deployment.

Follow the [merchant integration guide](https://docs.payai.network/x402/servers/batch-settlement) for the active policy and recovery requirements.

The SDK source is licensed under Apache-2.0; see [LICENSE](LICENSE) and [NOTICE](NOTICE).
