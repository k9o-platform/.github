# Kilimanjaro

Kilimanjaro is a modular developer platform for building secure enterprise applications.
You define AI agents, functions and data pipelines on the platform.
The SDKs let you deploy and invoke them, read and write your data, publish to and subscribe to streams,
sign users in, and encrypt with keys you hold.

## Architecture at a glance

![Architecture at a glance: your application and the k9o CLI call the Kilimanjaro API Gateway, which runs in your region or your environment and fronts Keep, Pulse, Gate, Kibo and the Governed Database, runs your agents and functions in Firelock, the sandbox for agents and functions, and records every call in the audit trail. Your own KMS or HSM keeps your keys (BYOK or HYOK) and Kibo encrypts against it on your machine.](https://raw.githubusercontent.com/k9o-platform/.github/main/profile/architecture-at-a-glance.svg)

Kilimanjaro can be deployed in supported regional public-cloud, private-cloud or air-gapped environments. Your application reaches it through an SDK or the `k9o` CLI. Both connect to the API Gateway, which exposes Keep, Pulse, Gate, Kibo and the Governed Database. Data changes, egress requests, and tool calls are recorded in the audit trail, including approvals and blocks.

Functions and agents configured for platform-hosted execution run in [Firelock](https://firelock-sandbox.github.io/), the open-source sandbox maintained by Kilimanjaro. In BYOK and HYOK modes, your key remains in your own KMS or HSM, and data you encrypt with Kibo is encrypted and decrypted in your application environment; the platform only ever receives it as ciphertext.

## Building blocks

- **Keep**: AI security and governance. Guardrails and policy for the agents you run.
- **Pulse**: data intelligence and real-time stream processing. Streams, analytics and live feeds.
- **Gate**: customer identity and access management. Sign-in and sessions, and automatic data scoping so a signed-in user reaches only their own data.
- **Kibo**: cryptographic keys and secrets management. Client-side encryption with keys you hold, and a secrets vault.

## Start here

1. **Pick your language** from the table below and install the SDK.
2. **Read the quick start** in that repository's README. It takes you from install to a first authenticated call.
3. **Browse the Developer Hub** for guides: <https://docs.kilimanjaro.dev>.

| Language | Package | Install | Repository |
|---|---|---|---|
| TypeScript / JavaScript | `@k9o/core` | `npm install @k9o/core` | [sdk-typescript](https://github.com/k9o-platform/sdk-typescript) |
| Python | `k9o` | `pip install k9o` | [sdk-python](https://github.com/k9o-platform/sdk-python) |
| Command line | `@k9o/cli` | `npm install -g @k9o/cli` | [k9o-cli](https://github.com/k9o-platform/k9o-cli) |
| Go | `k9o.dev/sdk-go` | `go get k9o.dev/sdk-go` | [sdk-go](https://github.com/k9o-platform/sdk-go) |
| Java | `dev.k9o:core` | Maven or Gradle, see the README | [sdk-java](https://github.com/k9o-platform/sdk-java) |
| .NET | `K9o.Core` | `dotnet add package K9o.Core` | [sdk-dotnet](https://github.com/k9o-platform/sdk-dotnet) |
| Rust | `k9o` | `cargo add k9o` | [sdk-rust](https://github.com/k9o-platform/sdk-rust) |
| Ruby | `k9o` | `gem install k9o` | [sdk-ruby](https://github.com/k9o-platform/sdk-ruby) |
| PHP | `k9o/sdk` | `composer require k9o/sdk` | [sdk-php](https://github.com/k9o-platform/sdk-php) |
| Swift | Swift package | Add `https://github.com/k9o-platform/sdk-swift` | [sdk-swift](https://github.com/k9o-platform/sdk-swift) |
| Flutter | `k9o_gate` | `flutter pub add k9o_gate` | [pub.dev](https://pub.dev/packages/k9o_gate) |
| React Native | `@k9o/gate-react-native` | `npm install @k9o/gate-react-native` | [npm](https://www.npmjs.com/package/@k9o/gate-react-native) |
| Kotlin / Android | | See the README | [sdk-kotlin](https://github.com/k9o-platform/sdk-kotlin) |

### Kibo: client-side encryption with keys you hold

Kibo packages encrypt and decrypt on your own machine or device against your own key management service, so the platform never sees plaintext or unwrapped keys.

| Platform | Package | Repository |
|---|---|---|
| TypeScript | [`@k9o/kibo`](https://www.npmjs.com/package/@k9o/kibo) | [sdk-kibo-typescript](https://github.com/k9o-platform/sdk-kibo-typescript) |
| .NET | [`K9o.Kibo`](https://www.nuget.org/packages/K9o.Kibo) | [sdk-kibo-dotnet](https://github.com/k9o-platform/sdk-kibo-dotnet) |
| Java | [`dev.k9o:kibo`](https://central.sonatype.com/artifact/dev.k9o/kibo) | [sdk-kibo-java](https://github.com/k9o-platform/sdk-kibo-java) |
| Go | `k9o.dev/sdk-go/kibo` | [sdk-go](https://github.com/k9o-platform/sdk-go) |
| Swift | Swift package | [sdk-kibo-swift](https://github.com/k9o-platform/sdk-kibo-swift) |
| React Native | `@k9o/kibo-react-native` | [sdk-kibo-react-native](https://github.com/k9o-platform/sdk-kibo-react-native) |

## Links

- Website: <https://kilimanjaro.dev>
- Documentation / Developer Hub: <https://docs.kilimanjaro.dev>
- Community extensions, examples and tools: <https://github.com/k9o-community>

## How these repositories work

Each repository is published from our monorepo and replaced with every release, which is why the history is one commit per release. Open issues here. Fixes ship in the next release. See [CONTRIBUTING](https://github.com/k9o-platform/.github/blob/main/CONTRIBUTING.md) for the details.

## Help

Questions and bugs: open an issue on the repository for your language, or email <engineering@kilimanjaro.dev>.
