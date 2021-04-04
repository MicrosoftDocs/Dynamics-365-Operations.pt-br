---
title: Componentes de administração de complemento do faturamento eletrônico
description: Este tópico fornece informações sobre os componentes relacionados à administração do complemento do faturamento eletrônico.
author: gionoder
manager: AnnBe
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 70ef47dd45200a14c9d780f3c280c554d0e52ac3
ms.sourcegitcommit: 543772ee97efe215cf6f2ec6e092cc1568919f20
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/13/2021
ms.locfileid: "5592565"
---
# <a name="electronic-invoicing-add-on-administration-components"></a>Componentes de administração de complemento do faturamento eletrônico

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Este tópico fornece informações sobre os componentes relacionados à administração do complemento do faturamento eletrônico. Ele também fornece informações sobre como configurar o serviço de complemento do faturamento eletrônico.

## <a name="azure"></a>Azure

Use o Microsoft Azure para criar os segredos para o cofre de chaves e a conta de armazenamento. Em seguida, use os segredos na configuração do complemento de faturamento eletrônico.

## <a name="lifecycle-services"></a>Lifecycle Services

Use o Lifecycle Services (LCS) do Microsoft Dynamics para habilitar o complemento dos microsserviços do projeto de implantação do LCS.

> [!NOTE]
> A instalação do complemento do microsserviço no LCS requer pelo menos uma máquina virtual de Camada 2. Para obter mais informações sobre o planejamento de ambiente, consulte [Planejamento de ambiente](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).
 

## <a name="regulatory-configuration-services"></a>Regulatory Configuration Services

O Regulatory Configuration Services (RCS) do Dynamics 365 é a interface usada para configurar o complemento do faturamento eletrônico. Recursos como ambientes e recursos de faturamento eletrônico são criados, mantidos e hospedados no RCS. Quando os recursos estão prontos, eles são publicados no serviço de complemento do faturamento eletrônico.

Para inscrição no RCS, consulte [Regulatory services](https://marketing.configure.global.dynamics.com/).

Para obter mais informações sobre RCS, consulte [Regulatory Configuration Services (RCS) — Recursos de globalização](rcs-globalization-feature.md)

### <a name="integration-with-the-electronic-invoicing-add-on"></a>Integração ao complemento do faturamento eletrônico

Para poder usar o RCS para configurar faturas eletrônicas, é necessário configurar o RCS para permitir a comunicação com o complemento do faturamento eletrônico. Você preenche essa configuração na guia **Complemento do faturamento eletrônico** da página **Parâmetros de relatórios eletrônicos**.

#### <a name="service-endpoint"></a>Empresa do serviço

O complemento de faturamento eletrônico está disponível em várias regiões geográficas do datacenter do Azure. A seguinte tabela lista a disponibilidade por região.

| Geografia do data center Azure |
|----------------------------|
| Leste dos EUA                    |
| Oeste dos EUA                    |
| Norte da UE                   |
| Oeste da UE                    |

### <a name="service-environments"></a>Ambientes de serviço

Os ambientes de serviço são partições lógicas criadas para oferecer suporte à execução de recursos de faturamento eletrônico no complemento de faturamento eletrônico. Os segredos de segurança e os certificados digitais e a governança (ou seja, permissões de acesso) devem ser configurados em nível do ambiente de serviço.

Os clientes podem criar a quantidade de ambientes de serviço desejada. Todos os ambientes de serviço que um cliente cria são independentes um do outro.

Os ambientes de serviço devem ser criados e mantidos no RCS. Quando os ambientes de serviço estão prontos, eles devem ser publicados no complemento do faturamento eletrônico.

#### <a name="service-environment-status"></a>Status do ambiente de serviço

Os ambientes de serviço podem ser gerenciados por meio do status. As opções possíveis são:

- **Não publicado** – o ambiente foi criado, mas ainda não foi publicado.
- **Publicado** – o ambiente foi publicado no complemento de faturamento eletrônico.
- **Alterado** – os atributos de um ambiente publicado foram alterados, mas as alterações ainda não foram publicadas.

#### <a name="customer-secrets"></a>Segredos do cliente

O serviço do complemento de faturamento eletrônico é responsável pelo armazenamento de todos os dados comerciais nos recursos do Azure pertencentes à sua empresa. Para garantir que o serviço funcione corretamente e que todos os dados comerciais exigidos e gerados pelo complemento de faturamento eletrônico sejam acessados somente pelo complemento, crie dois recursos principais do Azure:

- Uma conta de armazenamento do Azure (armazenamento de Blob) que armazenará faturas eletrônicas
- Um Azure Key Vault que armazenará certificados e o URI (Uniform Resource Identifier) da conta de armazenamento

> [!NOTE]
> Um cofre de chaves dedicado e uma conta de armazenamento de cliente devem ser alocados especificamente para uso com o complemento de faturamento eletrônico.

Para obter mais informações, consulte [Criar uma conta de armazenamento do Azure e um cofre de chaves](e-invoicing-create-azure-storage-account-key-vault.md).

#### <a name="users"></a>Usuários

Cada ambiente de serviço deve listar os usuários que podem se conectar ao Dynamics 365 Finance e ao Dynamics 365 Supply Chain Management no complemento de faturamento eletrônico.

#### <a name="publication"></a>Publicação

Os ambientes de serviço devem ser publicados no complemento de faturamento eletrônico antes de serem usados. Somente ambientes publicados podem ser acessados pelo Finance e pelo Supply Chain Management. Além disso, um ambiente de serviço deve ser publicado antes que as atualizações de seus atributos tenham efeito no serviço de faturamento eletrônico.

### <a name="connected-applications"></a>Aplicativos conectados

Os aplicativos conectados são as instâncias do Finance e do Supply Chain Management que você pode querer alcançar por meio do RCS. Além da URL do aplicativo e de seu locatário, um aplicativo conectado contém as credenciais que habilitam RCS a conectar-se ao ambiente.

Por meio dos aplicativos conectados, você pode configurar parte do recurso de faturamento eletrônico no Finance e no Supply Chain Management para que todo o recurso de faturamento eletrônico funcione.

## <a name="finance-and-supply-chain-management"></a>Finance e Supply Chain Management

### <a name="integration-with-electronic-invoicing-add-on"></a>Integração ao complemento do faturamento eletrônico

Antes de usar o Finance e o Supply Chain Management para emitir faturas eletrônicas por meio do complemento de faturamento eletrônico, configure o complemento para permitir a comunicação com o serviço.

#### <a name="electronic-invoicing-add-on-integration-feature"></a>Recurso de integração de complemento de faturamento eletrônico

Para habilitar a comunicação entre o Finance e o Supply Chain Management e o complemento de faturamento eletrônico, você deve ativar o recurso **Integração de complemento de faturamento eletrônico** no espaço de trabalho **Gerenciamento de recursos**.

#### <a name="service-endpoint"></a>Empresa do serviço

A empresa de serviço é a URL na qual o complemento do faturamento eletrônico está localizado. Antes da emissão de faturas eletrônicas, o ponto de extremidade de serviço deve ser configurado no Finance e no Supply Chain Management para emitir a comunicação com o serviço.

Para configurar o ponto de extremidade de serviço, acesse **Administração da organização \> Configuração \> Parâmetro de documento eletrônico** e, depois, na guia **Serviços de envio**, no campo **URL do complemento de faturamento eletrônico**, insira a URL, conforme descrito na tabela descrita na seção **Ponto de extremidade de serviço**.

#### <a name="environments"></a>Ambientes

O nome de ambiente que é inserido no Finance e no Supply Chain Management se refere ao nome do ambiente criado no RCS e publicado no complemento de faturamento eletrônico.

O ambiente deve ser configurado na guia **Serviços de envio** da página **Parâmetro de documento eletrônico**, de forma que cada solicitação para emitir faturas eletrônicas contenha o ambiente no qual o complemento de faturamento eletrônico possa determinar qual recurso de faturamento eletrônico deve processar a solicitação.

## <a name="additional-resources"></a>Recursos adicionais

- [Configurar faturas eletrônicas no RCS](e-invoicing-configuration-rcs.md)
- [Emitir faturas eletrônicas no Finance e no Supply Chain Management](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
