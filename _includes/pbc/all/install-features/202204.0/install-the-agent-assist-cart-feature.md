

This document describes how to integrate the Agent Assist + Cart feature into a Spryker project.

## Prerequisites

To start the feature integration, overview and install the necessary features:

| NAME         | VERSION | INTEGRATION GUIDE                                            |
| ------------ | ------- | ------------------------------------------------------------ |
| Spryker Core | {{site.version}}  | [Spryker Сore feature integration](/docs/scos/dev/feature-integration-guides/{{site.version}}/spryker-core-feature-integration.html) |
| Agent Assist | {{site.version}}  | [Install the Agent Assist feature](/docs/pbc/all/user-management/{{site.version}}/install-and-upgrade/install-the-agent-assist-feature.html) |
| Cart         | {{site.version}}  | [Install the Cart Glue API](/docs/scos/dev/feature-integration-guides/{{site.version}}/glue-api/glue-api-cart-feature-integration.html) |


## 1) Set up behavior

Activate the following plugins:

| PLUGIN   | SPECIFICATION   | PREREQUISITES | NAMESPACE   |
| -------------------- | -------------------- | ------------- | -------------------- |
| SanitizeCustomerQuoteImpersonationSessionFinisherPlugin | Sanitizes a customer quote. | None          | Spryker\Client\Quote\Plugin\Agent |

**src/Pyz/Client/Agent/AgentDependencyProvider.php**

```php
<?php

namespace Pyz\Client\Agent;

use Spryker\Client\Agent\AgentDependencyProvider as SprykerAgentDependencyProvider;
use Spryker\Client\Quote\Plugin\Agent\SanitizeCustomerQuoteImpersonationSessionFinisherPlugin;

class AgentDependencyProvider extends SprykerAgentDependencyProvider
{
    /**
     * @return \Spryker\Client\AgentExtension\Dependency\Plugin\ImpersonationSessionFinisherPluginInterface[]
     */
    protected function getImpersonationSessionFinisherPlugins(): array
    {
        return [
            new SanitizeCustomerQuoteImpersonationSessionFinisherPlugin(),
        ];
    }
}
```

{% info_block warningBox "Verification" %}

Ensure that, after finishing a customer impersonation, the session quote is empty.

{% endinfo_block %}


## Related features

Integrate the following related features:

| FEATURE   | REQUIRED FOR THE CURRENT FEATURE | INTEGRATION GUIDE  |
| ----------------- | ------------ | ----------------------- |
| Agent Assist + Shopping List |         | [Agent Assist + Shopping List feature integration](/docs/pbc/all/user-management/{{site.version}}/install-and-upgrade/install-the-agent-assist-shopping-list-feature.html) |
