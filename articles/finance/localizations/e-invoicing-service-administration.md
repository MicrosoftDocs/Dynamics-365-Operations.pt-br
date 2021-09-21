---
title: Componentes de administração de Faturamento eletrônico
description: Este tópico fornece informações sobre os componentes relacionados à administração do Faturamento eletrônico.
author: gionoder
ms.date: 08/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: d187e8a03552258099d7021ff056d0726ea60ca1
ms.sourcegitcommit: baf82100f0aa7d5f5f47c7f54bc155d8a07beab5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/31/2021
ms.locfileid: "7463865"
---
# <a name="electronic-invoicing-administration-components"></a>Componentes de administração de Faturamento eletrônico

[!include [banner](../includes/banner.md)]


Este tópico fornece informações sobre os componentes relacionados à administração do Faturamento eletrônico. Ele também fornece informações sobre como configurar o serviço de Faturamento eletrônico.

## <a name="azure"></a>Azure

Use o Microsoft Azure para criar os segredos para o Key Vault e configurar uma conta de armazenamento. Em seguida, use os segredos do Key Vault e o token SAS da conta de armazenamento na configuração do Faturamento eletrônico.

## <a name="lifecycle-services"></a>Lifecycle Services

Use o Lifecycle Services (LCS) do Microsoft Dynamics para habilitar o Suplemento do Faturamento eletrônico do projeto de implantação do LCS.

> [!NOTE]
> A instalação dos suplementos no LCS requer pelo menos um **Ambiente de camada 2**. Para obter mais informações sobre o planejamento de ambiente, consulte [Planejamento de ambiente](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).
 

## <a name="regulatory-configuration-services"></a>Regulatory Configuration Services

O Regulatory Configuration Services (RCS) do Dynamics 365 é a interface usada para configurar o Faturamento eletrônico. Recursos como ambientes e recursos de faturamento eletrônico são criados, mantidos e hospedados no RCS. Quando os recursos estão prontos, eles são publicados no serviço de Faturamento eletrônico.

Para inscrição no RCS, consulte [Regulatory services](https://marketing.configure.global.dynamics.com/).

Para obter mais informações sobre RCS, consulte [Regulatory Configuration Services (RCS) — Recursos de globalização](rcs-globalization-feature.md)

### <a name="integration-with-electronic-invoicing"></a>Integração ao Faturamento eletrônico 

Para poder usar o RCS para configurar faturas eletrônicas, é necessário configurar o RCS para permitir a comunicação com o Faturamento eletrônico. Você preenche essa configuração na guia **Faturamento eletrônico** da página **Parâmetros de relatórios eletrônicos**.

#### <a name="service-endpoint"></a><a id='svc-endpoint-uris'></a>Empresa do serviço

O Faturamento eletrônico está disponível em várias regiões do datacenter do Azure. A seguinte tabela lista a disponibilidade por região.


| Geografia do data center Azure | URI do ponto de extremidade do serviço                                                       |
|----------------------------|----------------------------------------------------------------------------|
| Estados Unidos              | <p>https://gw.us-il101.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.us-il102.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.us-il103.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.us-il104.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.us-il105.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.us-il106.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.us-il107.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.us-il108.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.us-il109.gateway.prod.island.powerapps.com/electronicinvoicing</p> |
| Europa                     | <p>https://gw.eu-il101.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.eu-il102.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.eu-il103.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.eu-il104.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.eu-il105.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.eu-il106.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.eu-il107.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.eu-il108.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.eu-il109.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.eu-il110.gateway.prod.island.powerapps.com/electronicinvoicing/</p> |
| Reino Unido             | <p>https://gw.uk-il101.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.uk-il102.gateway.prod.island.powerapps.com/electronicinvoicing/</p> |
| Ásia                       | <p>https://gw.as-il101.gateway.prod.island.powerapps.com/electronicinvoicing/</p><p>https://gw.as-il102.gateway.prod.island.powerapps.com/electronicinvoicing/</p> |

### <a name="service-environments"></a>Ambientes de serviço

Os ambientes de serviço são partições lógicas criadas para oferecer suporte à execução de recursos de globalização no Faturamento eletrônico. Os segredos de segurança e os certificados digitais e a governança (ou seja, permissões de acesso) devem ser configurados em nível do ambiente de serviço.

Os clientes podem criar a quantidade de ambientes de serviço desejada. Todos os ambientes de serviço que um cliente cria são independentes um do outro.

Os ambientes de serviço devem ser criados e mantidos no RCS. Quando os ambientes de serviço estão prontos, eles devem ser publicados no Faturamento eletrônico.

#### <a name="service-environment-status"></a>Status do ambiente de serviço

Os ambientes de serviço podem ser gerenciados por meio do status. As opções possíveis são:

- **Não publicado** – o ambiente foi criado, mas ainda não foi publicado.
- **Publicado** – o ambiente foi publicado no Faturamento eletrônico.
- **Alterado** – os atributos de um ambiente publicado foram alterados, mas as alterações ainda não foram publicadas.

#### <a name="customer-secrets"></a>Segredos do cliente

O serviço de Faturamento eletrônico é responsável pelo armazenamento de todos os dados comerciais nos recursos do Azure pertencentes à sua empresa. Para garantir que o serviço funcione corretamente e que todos os dados comerciais necessários e gerados pelo Faturamento eletrônico sejam acessados corretamente, crie dois recursos principais do Azure:

- Uma conta de armazenamento do Azure (Armazenamento de Blobs) que armazenará documentos eletrônicos, incluindo faturas eletrônicas, resultados de transformações de documentos e respostas de serviços Web externos.
- Um Azure Key Vault que armazenará certificados e o URI (Uniform Resource Identifier) da conta de armazenamento (token SAS).


Um Key Vault dedicado e uma conta de armazenamento de cliente devem ser alocados especificamente para uso com o Faturamento Eletrônico. Para obter mais informações, consulte [Criar uma conta de armazenamento do Azure e um Key Vault](e-invoicing-create-azure-storage-account-key-vault.md).

Para monitorar a integridade do Key Vault e receber alertas, configure o Azure Monitor para o Key Vault. Ao habilitar o log do Key Vault, você pode monitorar como, quando e por quem seus Key Vaults são acessados. Para obter mais informações, consulte [Monitorar e alertar para o Azure Key Vault](/azure/key-vault/general/alert) e [Como habilitar o log do Key Vault](/azure/key-vault/general/howto-logging?tabs=azure-cli).

Como prática recomendada, gire periodicamente os segredos. Para obter mais informações, consulte [Documentação de segredos](/azure/key-vault/secrets/).

#### <a name="users"></a>Usuários

Cada ambiente de serviço deve listar os usuários que podem se conectar ao Dynamics 365 Finance e ao Dynamics 365 Supply Chain Management no Faturamento eletrônico.

#### <a name="publication"></a>Publicação

Os ambientes de serviço devem ser publicados no Faturamento eletrônico antes de serem usados. Somente ambientes publicados podem ser acessados pelo Finance e pelo Supply Chain Management. Além disso, um ambiente de serviço deve ser publicado antes que as atualizações de seus atributos tenham efeito no serviço de faturamento eletrônico.

### <a name="connected-applications"></a>Aplicativos conectados

Os aplicativos conectados são as instâncias do Finance e do Supply Chain Management que você pode querer alcançar por meio do RCS. Além da URL do aplicativo e de seu locatário, um aplicativo conectado contém as credenciais que habilitam RCS a conectar-se ao ambiente.

Por meio dos aplicativos conectados, você pode configurar parte do recurso de faturamento eletrônico no Finance e no Supply Chain Management para que todo o recurso de faturamento eletrônico funcione.

## <a name="finance-and-supply-chain-management"></a>Finance e Supply Chain Management

### <a name="integration-with-electronic-invoicing"></a>Integração ao Faturamento eletrônico

Antes de usar o Finance e o Supply Chain Management para emitir faturas eletrônicas por meio do Faturamento eletrônico, ele deve ser configurado para permitir a comunicação com o serviço.

#### <a name="electronic-invoicing-integration-feature"></a>Recurso de integração de faturamento eletrônico

Para habilitar a comunicação entre o Finance e o Supply Chain Management e o Faturamento eletrônico, você deve ativar o recurso **Integração de Faturamento eletrônico** no espaço de trabalho **Gerenciamento de recursos**.

#### <a name="service-endpoint"></a>Empresa do serviço

A empresa de serviço é a URL na qual o Faturamento eletrônico está localizado. Antes da emissão de faturas eletrônicas, o ponto de extremidade de serviço deve ser configurado no Finance e no Supply Chain Management para emitir a comunicação com o serviço.

Para configurar o ponto de extremidade de serviço, acesse **Administração da organização \> Configuração \> Parâmetros de documento eletrônico** e, depois, na guia **Faturamento eletrônico**, no campo **URL do ponto de extremidade**, insira a URL apropriada da tabela descrita na seção [Ponto de extremidade de serviço](#svc-endpoint-uris) anteriormente neste tópico.

#### <a name="environments"></a>Ambientes

O nome de ambiente que é inserido no Finance e no Supply Chain Management se refere ao nome do ambiente criado no RCS e publicado no Faturamento eletrônico.

O ambiente precisa ser configurado na guia **Faturamento eletrônico** da página **Parâmetros do documento eletrônico**. Dessa forma, cada solicitação de emissão de faturas eletrônicas contém o ambiente no qual o Faturamento eletrônico pode determinar qual recurso de faturamento eletrônico precisa processar a solicitação.

## <a name="additional-resources"></a>Recursos adicionais

- [Configurar faturas eletrônicas no RCS](e-invoicing-configuration-rcs.md)
- [Emitir faturas eletrônicas no Finance e no Supply Chain Management](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
