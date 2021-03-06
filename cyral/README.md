# Agent Check: Cyral

## Overview

This check monitors a [Cyral][1] MySQL sidecar through the Datadog Agent.

## Setup

Follow the instructions below to install and configure this check for an Agent running on a host. For containerized environments, see the [Autodiscovery Integration Templates][2] for guidance on applying these instructions.

### Installation

If you are using Agent v6.8+ follow the instructions below to install the Cyral check on your host. See the dedicated Agent guide for [installing community integrations][3] to install checks with the [Agent prior v6.8][4] or the [Docker Agent][5]:

1. [Download and launch the Datadog Agent][9].
2. Run the following command to install the integrations wheel with the Agent:

   ```shell
   datadog-agent integration install -t datadog-cyral==<INTEGRATION_VERSION>
   ```

3. Configure your integration like [any other packaged integration][7].

### Configuration

1. Edit the `cyral.d/conf.yaml` file, in the `conf.d/` folder at the root of your Agent's configuration directory to start collecting your cyral performance data. See the [sample cyral.d/conf.yaml][8] for all available configuration options.

    ```yaml
    init_config:

    instances:
     # url of the metrics endpoint of prometheus
     - prometheus_url: http://localhost:9018/metrics
    ```

2. [Restart the Agent][9].

### Validation

[Run the Agent's status subcommand][10] and look for `cyral` under the Checks section.

## Data Collected

### Metrics

See [metadata.csv][11] for a list of metrics provided by this check.

### Service Checks

Cyral does not include any service checks.

### Events

Cyral does not include any events.

## Troubleshooting

### Agent cannot connect

```text
    cyral
    -------
      - instance #0 [ERROR]: "('Connection aborted.', error(111, 'Connection refused'))"
      - Collected 0 metrics, 0 events & 0 service check
```

Check that the `url` in `cyral.yaml` is correct.

Need help? Contact [Datadog support][12].

[1]: https://cyral.com/
[2]: https://docs.datadoghq.com/agent/kubernetes/integrations/
[3]: https://docs.datadoghq.com/agent/guide/community-integrations-installation-with-docker-agent/
[4]: https://docs.datadoghq.com/agent/guide/community-integrations-installation-with-docker-agent/?tab=agentpriorto68
[5]: https://docs.datadoghq.com/agent/guide/community-integrations-installation-with-docker-agent/?tab=docker
[6]: https://app.datadoghq.com/account/settings#agent
[7]: https://docs.datadoghq.com/getting_started/integrations/
[8]: https://github.com/DataDog/integrations-extras/blob/master/cyral/datadog_checks/cyral/data/conf.yaml.example
[9]: https://docs.datadoghq.com/agent/guide/agent-commands/#start-stop-and-restart-the-agent
[10]: https://docs.datadoghq.com/agent/guide/agent-commands/#agent-status-and-information
[11]: https://github.com/DataDog/integrations-extras/blob/master/cyral/metadata.csv
[12]: https://docs.datadoghq.com/help/
