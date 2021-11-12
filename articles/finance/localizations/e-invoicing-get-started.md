---
title: Introdução ao Faturamento eletrônico
description: Este tópico fornece informações que ajudarão você a começar a usar o Faturamento eletrônico no Microsoft Dynamics 365 Finance e no Dynamics 365 Supply Chain Management.
author: gionoder
ms.date: 08/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: d0550228dc77ed255a0033bc3b0a4ec21d48a497
ms.sourcegitcommit: 2113678369f47944f8725ca656f461fa159f87f6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2021
ms.locfileid: "7700370"
---
# <a name="get-started-with-electronic-invoicing"></a>Introdução ao Faturamento eletrônico

[!include [banner](../includes/banner.md)]

Este tópico fornece informações que ajudarão você a começar a usar o Faturamento eletrônico. Este tópico orienta você ao longo das etapas de configuração comuns em Regulatory Configuration Services (RCS) e Dynamics 365 Finance, além de fornecer as etapas que deve seguir para enviar documentos comerciais e revisar os resultados de processamento.

## <a name="prerequisites"></a>Pré-requisitos

Antes de concluir os procedimentos neste tópico, é preciso ter os seguintes pré-requisitos em vigor:

- Configure o ambiente do Microsoft Dynamics Lifecycle Services (LCS), Regulatory Configuration Service (RCS) e o Microsoft Dynamics 365 Finance ou Dynamics 365 Supply Chain Management. Para obter mais informações, consulte [introdução à administração do serviço de Faturamento eletrônico](e-invoicing-get-started-service-administration.md).
- Crie um provedor de configuração para sua organização. Para obter mais informações, consulte [Criar um provedor de configuração e marcá-lo como ativo.](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider"></a>Importar um recurso de faturamento eletrônico do provedor de configuração da Microsoft 

1. Entre na conta RCS (serviço de configuração regulatória).
2. No espaço de trabalho **Recursos de globalização** na seção **Recursos**, selecione o bloco **Faturamento eletrônico**.
3. Selecione **Importar** e, em seguida, **Sincronizar**.
4. Filtre a coluna **Provedor de configuração** pelo termo **Microsoft**.
5. Selecione o nome de um recurso de Faturamento eletrônico na tabela e, em seguida, **Importar**.

## <a name="create-an-electronic-invoicing-feature-under-your-organization-provider"></a>Crie um recurso Faturamento eletrônico para o provedor da sua organização

1. No RCS, na seção **Recursos** do espaço de trabalho **Recursos de globalização**, selecione o bloco **Faturamento eletrônico**.
2. Selecione **Adicionar** > **Baseado em recurso existente** e, no campo **Nome**, insira o nome do recurso de faturamento eletrônico.
3. No campo **Descrição**, insira uma descrição do recurso.
4. No campo **Recurso base**, selecione o recurso de faturamento eletrônico importado do provedor de configuração da Microsoft.
5. Selecione **Criar recurso**.

## <a name="country-specific-configuration-for-electronic-invoicing-feature"></a>Configuração específica de país para o recurso Faturamento eletrônico

Dependendo do país ou da região, o recurso de Faturamento eletrônico pode exigir configuração específica. 

Para obter as etapas específicas, consulte a documentação "Introdução" que está disponível para seu país ou região.

## <a name="import-the-model-mapping-configurations-from-electronic-reporting"></a>Importar as configurações de mapeamentos de modelo de Relatórios eletrônicos

1. No RCS, selecione o espaço de trabalho **Relatório eletrônico**.
2. Na lista de provedores de Configuração **Microsoft**, selecione **Repositórios**.
3. Selecione **Global** e, no Painel de Ações, selecione **Abrir**.
4. Importe as configurações de mapeamento de modelos de acordo com a seguinte tabela por nome de recurso.

| Nome do recurso                         | Configuração de mapeamento de modelos |
|--------------------------------------|-----------------------------|
| Faturas eletrônicas austríacas (AT)    | <p>Modelo de contexto de fatura de cliente</p><p>Modelo de fatura</p> |
| Fatura eletrônica belga (BE)      | <p>Modelo de contexto de fatura de cliente</p><p>Modelo de fatura</p> |
| NF-e brasileira (BR)                  | <p>Modelo de contexto de fatura de cliente</p><p>Notas fiscais</p><p>Modelo de mensagem de resposta</p> |
| NFS-e ABRASF Curitiba brasileira (BR) | <p>Modelo de contexto de fatura de cliente</p><p>Notas fiscais</p><p>Modelo de mensagem de resposta</p> |
| Fatura eletrônica dinamarquesa (DK)       | <p>Modelo de contexto de fatura de cliente</p><p>Modelo de fatura</p> |
| Fatura eletrônica egípcia (EG)     | <p>Modelo de contexto de fatura de cliente</p><p>Modelo de fatura</p><p>Modelo de mensagem de resposta</p> |
| Fatura eletrônica estoniana (EE)     | <p>Modelo de contexto de fatura de cliente</p><p>Modelo de fatura</p> |
| Fatura eletrônica finlandesa (FI)       | <p>Modelo de contexto de fatura de cliente</p><p>Modelo de fatura</p> |
| Fatura eletrônica francesa (FR)       | <p>Modelo de contexto de fatura de cliente</p><p>Modelo de fatura</p> |
| Fatura eletrônica alemã (DE)       | <p>Modelo de contexto de fatura de cliente</p><p>Modelo de fatura</p> |
| FatturaPA (IT)                       | <p>Modelo de contexto de fatura de cliente</p><p>Modelo de fatura</p> |
| CFDI Interfactura mexicana (MX)       | <p>Modelo de contexto de fatura de cliente</p><p>Modelo de fatura</p><p>Modelo de mensagem de resposta</p> |
| Fatura eletrônica holandesa (NL)        | <p>Modelo de contexto de fatura de cliente</p><p>Modelo de fatura</p> |
| Fatura eletrônica norueguesa (NO)    | <p>Modelo de contexto de fatura de cliente</p><p>Modelo de fatura</p> |
| Fatura eletrônica espanhola (ES)      | <p>Modelo de contexto de fatura de cliente</p><p>Modelo de fatura</p> |
| Fatura eletrônica PEPPOL            | <p>Modelo de contexto de fatura de cliente</p><p>Modelo de fatura</p> |
| Fatura da Arábia Saudita (SA)| <p>Modelo de contexto de fatura de cliente</p><p>Modelo de fatura</p> |


## <a name="configure-the-application-setup"></a>Definir a configuração do aplicativo

1. Selecione o recurso de faturamento eletrônico criado por você.
2. Na guia **Configurações**, selecione **Configuração do aplicativo**.
3. No campo **Conectar aplicativo**, selecione a conexão que está associada à sua instância do Finance ou Supply Chain Management.
4. Na seção **Tipos de documento eletrônico**, selecione **Adicionar**.
5. Selecione e insira um valor para **Nome da tabela** de acordo com a seguinte tabela.

    | Nome do recurso                         | Documento comercial | Nome da tabela |
    |--------------------------------------|-------------------|------------|
    | Faturas eletrônicas austríacas (AT)    | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Diário de faturas de clientes</p><p>Fatura de projeto</p> |
    | Fatura eletrônica belga (BE)      | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Diário de faturas de clientes</p><p>Fatura de projeto</p> |
    | NF-e brasileira (BR)                  | <p>Nota fiscal</p><p>Carta de correção</p> | Nota fiscal |
    | NFS-e ABRASF Curitiba brasileira (BR) | Documento fiscal de serviço | Nota fiscal |
    | Fatura eletrônica dinamarquesa (DK)       | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Diário de faturas de clientes</p><p>Fatura de projeto</p> |
    | Fatura eletrônica egípcia (EG)     | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Diário de faturas de clientes</p><p>Fatura de projeto</p> |
    | Fatura eletrônica estoniana (EE)     | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Diário de faturas de clientes</p><p>Fatura de projeto</p> |
    | Fatura eletrônica finlandesa (FI)       | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Diário de faturas de clientes</p><p>Fatura de projeto</p> |
    | Fatura eletrônica francesa (FR)       | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Diário de faturas de clientes</p><p>Fatura de projeto</p> |
    | Fatura eletrônica alemã (DE)       | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Diário de faturas de clientes</p><p>Fatura de projeto</p> |
    | FatturaPA (IT)                       | <p>Fatura de venda</p><p>Fatura de projeto | <p>Diário de faturas de clientes</p><p>Fatura de projeto</p> |
    | CFDI Interfactura mexicana (MX)       | <p>Fatura de venda</p><p>Guia de Remessa</p><p>Transferência de estoque</p><p>Complemento de pagamento</p> | Diário de faturas de clientes |
    | Fatura eletrônica holandesa (NL)        | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Diário de faturas de clientes</p><p>Fatura de projeto</p> |
    | Fatura eletrônica norueguesa (NO)    | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Diário de faturas de clientes</p><p>Fatura de projeto</p> |
    | Fatura eletrônica espanhola (ES)      | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Diário de faturas de clientes</p><p>Fatura de projeto</p> |
    | Fatura eletrônica PEPPOL            | <p>Fatura de venda</p><p>Fatura do projeto</p> | <p>Diário de faturas de clientes</p><p>Fatura do projeto</p> |
    | Fatura da Arábia Saudita (SA)| <p>Fatura de venda</p><p>Fatura do projeto</p> | <p>Diário de faturas de clientes</p><p>Fatura do projeto</p> |

6. Para cada nome de tabela criado, selecione e insira um valor de contexto de acordo com a seguinte tabela.

    | Nome do recurso                         | Documento comercial | Contexto |
    |--------------------------------------|-------------------|---------|
    | Faturas eletrônicas austríacas (AT)    | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Modelo de contexto de fatura de cliente – contexto de fatura de cliente</p><p>Modelo de contexto de fatura de cliente – contexto de fatura de projeto</p> |
    | Fatura eletrônica belga (BE)      | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Modelo de contexto de fatura de cliente – contexto de fatura de cliente</p><p>Modelo de contexto de fatura de cliente – contexto de fatura de projeto</p> |
    | NF-e brasileira (BR)                  | <p>Nota fiscal</p><p>Carta de correção</p> | <p>Modelo de contexto de fatura de cliente – contexto de nota fiscal</p><p>Modelo de contexto de fatura de cliente – contexto de carta de correção FD</p> |
    | NFS-e ABRASF Curitiba brasileira (BR) | Documento fiscal de serviço| Modelo de contexto de fatura de cliente – contexto de nota fiscal |
    | Fatura eletrônica dinamarquesa (DK)       | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Modelo de contexto de fatura de cliente – contexto de fatura de cliente</p><p>Modelo de contexto de fatura de cliente – contexto de fatura de projeto</p> |
    | Fatura eletrônica egípcia (EG)     | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Modelo de contexto de fatura de cliente – contexto de fatura de cliente</p><p>Modelo de contexto de fatura de cliente – contexto de fatura de projeto</p> |
    | Fatura eletrônica estoniana (EE)     | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Modelo de contexto de fatura de cliente – contexto de fatura de cliente</p><p>Modelo de contexto de fatura de cliente – contexto de fatura de projeto</p> |
    | Fatura eletrônica finlandesa (FI)       | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Modelo de contexto de fatura de cliente – contexto de fatura de cliente</p><p>Modelo de contexto de fatura de cliente – contexto de fatura de projeto</p> |
    | Fatura eletrônica francesa (FR)       | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Modelo de contexto de fatura de cliente – contexto de fatura de cliente</p><p>Modelo de contexto de fatura de cliente – contexto de fatura de projeto</p> |
    | Fatura eletrônica alemã (DE)       | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Modelo de contexto de fatura de cliente – contexto de fatura de cliente</p><p>Modelo de contexto de fatura de cliente – contexto de fatura de projeto</p> |
    | FatturaPA (IT)                       | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Modelo de contexto de fatura de cliente – contexto de fatura de cliente</p><p>Modelo de contexto de fatura de cliente – contexto de fatura de projeto</p> |
    | CFDI Interfactura mexicana (MX)       | <p>Fatura de venda</p><p>Guia de Remessa</p><p>Transferência de estoque</p><p>Complemento de pagamento</p> | Modelo de contexto de fatura de cliente – contexto de fatura de cliente |
    | Fatura eletrônica holandesa (NL)        | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Modelo de contexto de fatura de cliente – contexto de fatura de cliente</p><p>Modelo de contexto de fatura de cliente – contexto de fatura de projeto</p> |
    | Fatura eletrônica norueguesa (NO)    | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Modelo de contexto de fatura de cliente – contexto de fatura de cliente</p><p>Modelo de contexto de fatura de cliente – contexto de fatura de projeto</p> |
    | Fatura eletrônica espanhola (ES)      | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Modelo de contexto de fatura de cliente – contexto de fatura de cliente</p><p>Modelo de contexto de fatura de cliente – contexto de fatura de projeto</p> |
    | Fatura eletrônica PEPPOL            | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Modelo de contexto de fatura de cliente – contexto de fatura de cliente</p><p>Modelo de contexto de fatura de cliente – contexto de fatura de projeto</p> |
    | Fatura da Arábia Saudita (SA)| <p>Fatura de venda</p><p>Fatura do projeto</p> | <p>Modelo de contexto de fatura de cliente – contexto de fatura de cliente</p><p>Modelo de contexto de fatura de cliente – contexto de fatura de projeto</p> |

7. Para cada nome e contexto de tabela, selecione e insira um valor para o mapeamento de documentos comerciais de acordo com a tabela a seguir.

    | Nome do recurso                         | Documento comercial | Mapeamento de documento comercial |
    |--------------------------------------|-------------------|---------------------------|
    | Faturas eletrônicas austríacas (AT)    | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Mapeamento de modelo de fatura – fatura de cliente</p><p>Mapeamento de modelo de fatura – fatura de projeto</p> |
    | Fatura eletrônica belga (BE)      | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Mapeamento de modelo de fatura – fatura de cliente</p><p>Mapeamento de modelo de fatura – fatura de projeto</p> |
    | NF-e brasileira (BR)                  | <p>Nota fiscal</p><p>Carta de correção</p> | <p>Mapeamento de nota fiscal – mapeamento de nota fiscal</p><p>Mapeamento de nota fiscal – mapeamento de carta de correção</p> |
    | NFS-e ABRASF Curitiba brasileira (BR) | Documento fiscal de serviço | Mapeamento de nota fiscal – mapeamento de nota fiscal |
    | Fatura eletrônica dinamarquesa (DK)       | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Mapeamento de modelo de fatura – fatura de cliente</p><p>Mapeamento de modelo de fatura – fatura de projeto</p> |
    | Fatura eletrônica egípcia (EG)     | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Mapeamento de modelo de fatura – fatura de cliente</p><p>Mapeamento de modelo de fatura – fatura de projeto</p> |
    | Fatura eletrônica estoniana (EE)     | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Mapeamento de modelo de fatura – fatura de cliente</p><p>Mapeamento de modelo de fatura – fatura de projeto</p> |
    | Fatura eletrônica finlandesa (FI)       | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Mapeamento de modelo de fatura – fatura de cliente</p><p>Mapeamento de modelo de fatura – fatura de projeto</p> |
    | Fatura eletrônica francesa (FR)       | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Mapeamento de modelo de fatura – fatura de cliente</p><p>Mapeamento de modelo de fatura – fatura de projeto</p> |
    | Fatura eletrônica alemã (DE)       | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Mapeamento de modelo de fatura – fatura de cliente</p><p>Mapeamento de modelo de fatura – fatura de projeto</p> |
    | FatturaPA (IT)                       | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Mapeamento de modelo de fatura – fatura de cliente</p><p>Mapeamento de modelo de fatura – fatura de projeto</p> |
    | CFDI Interfactura mexicana (MX)       | <p>Fatura de venda</p><p>Guia de Remessa</p><p>Transferência de estoque</p><p>Complemento de pagamento</p> | Mapeamento de modelo de fatura – fatura de cliente |
    | Fatura eletrônica holandesa (NL)        | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Mapeamento de modelo de fatura – fatura de cliente</p><p>Mapeamento de modelo de fatura – fatura de projeto</p> |
    | Fatura eletrônica norueguesa (NO)    | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Mapeamento de modelo de fatura – fatura de cliente</p><p>Mapeamento de modelo de fatura – fatura de projeto</p> |
    | Fatura eletrônica espanhola (ES)      | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Mapeamento de modelo de fatura – fatura de cliente</p><p>Mapeamento de modelo de fatura – fatura de projeto</p> |
    | Fatura eletrônica PEPPOL            | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Mapeamento de modelo de fatura – fatura de cliente</p><p>Mapeamento de modelo de fatura – fatura de projeto</p> |
    | Fatura da Arábia Saudita (SA)| <p>Fatura de venda</p><p>Fatura do projeto</p> | <p>Mapeamento de modelo de fatura – fatura de cliente</p><p>Mapeamento de modelo de fatura – fatura de projeto</p> |


## <a name="country-specific-configuration-of-application-setup"></a>Configuração específica do país para a configuração do aplicativo

Dependendo do país ou da região, a configuração do Aplicativo pode exigir configuração específica. 

Para obter as etapas específicas, consulte a documentação "Introdução" que está disponível para seu país ou região.

## <a name="deploy-the-electronic-invoicing-feature-to-service-environment"></a>Implantar o recurso de Faturamento eletrônico no ambiente do Serviço

1. Na guia **Versões**, selecione a versão do recurso de faturamento eletrônico que você deseja implantar.
2. Selecione **Alterar status** \> **Concluir**.
3. Selecione **Alterar status** \> **Publicar**.
4. Selecione **Implantar**.
5. Defina a opção **Implantar para aplicativo conectado** como **Não**.
6. Defina a opção **Implantar para ambiente de serviço** como **Sim**.
7. No campo **Ambiente de serviço**, selecione o ambiente do serviço de Faturamento eletrônico em que deseja implantar o recurso de Faturamento eletrônico.
8. No campo **Data Inicial**, selecione a data em que o recurso de Faturamento eletrônico deve se tornar efetivo no Faturamento eletrônico.
9. Selecione **OK**.

## <a name="deploy-the-electronic-invoicing-feature-to-connected-application"></a>Implantar o recurso de Faturamento eletrônico ao aplicativo Conectado

1. Na guia **Versões**, selecione uma versão do recurso de faturamento eletrônico que você deseja implantar.
2. Selecione **Implantar**.
3. Defina a opção **Implantar para aplicativo conectado** como **Sim**.
4. No campo **Conectar aplicativo**, selecione a conexão que está associada à sua instância do Finance ou Supply Chain Management.
5. Defina a opção **Implantar no ambiente de serviço** como **Não**.
6. Selecione **OK**.

## <a name="turn-on-the-electronic-invoicing-feature-in-finance-or-supply-chain-management"></a>Ative o recurso de faturamento eletrônico no Finance ou no Supply Chain Management

1. Entre no Finance ou no Supply Chain Management e verifique se você está na entidade legal correta.
2. Acesse **Administração da organização** \> **Configuração** \> **Parâmetros de documentos eletrônicos**.
3. Na guia **Recursos**, selecione o recurso específico do país/região para ativar o recurso Faturamento eletrônico para o Finance ou o Supply Chain Management. A tabela a seguir fornece uma lista dos recursos de faturamento eletrônico disponíveis para países/regiões específicos. 

    | Nome do recurso                                          | País/região  |
    |-------------------------------------------------------|-----------------|
    | Faturas eletrônicas austríacas (AT)                     | Áustria         |
    | Fatura eletrônica belga (BE)                       | Bélgica         |
    | Fatura eletrônica mexicana CFDI (MX)                  | México          |
    | Fatura eletrônica dinamarquesa (DK)                        | Dinamarca         |
    | Fatura eletrônica holandesa (NL)                         | Os Países Baixos |
    | Fatura eletrônica egípcia (EG)                      | Egito           |
    | Fatura eletrônica estoniana (EE)                      | Estônia         |
    | Fatura eletrônica finlandesa (FI)                       | Finlândia         |
    | Fatura eletrônica francesa (FR)                        | França          |
    | Fatura eletrônica alemã (DE)                        | Alemanha         |
    | Fatura eletrônica italiana (TI)                       | Itália           |
    | NF-e Federal - Fatura eletrônica brasileira (BR)      | Brasil          |
    | NFS-e: fatura eletrônica de serviços brasileira (municipal)   | Brasil          |
    | Fatura eletrônica norueguesa (NO)                     | Noruega          |
    | Fatura eletrônica PEPPOL                             | Global          |
    | Fatura eletrônica espanhola (ES)                       | Espanha           |
    | Fatura da Arábia Saudita (SA)                 | Arábia Saudita    |
    

4. Selecione **Salvar**.

## <a name="issue-electronic-invoices"></a>Emitir faturas eletrônicas

1. Acesse **Administração da organização** \> **Periódico** \> **Documentos eletrônicos** \> **Enviar documentos eletrônicos**.
2. Na Guia Rápida **Registros a incluir**, selecione **Filtro**.
3. Selecione **Adicionar** para adicionar um nome de tabela ao filtro de consulta.
4. Selecione a tabela que contém as faturas.

    > [!NOTE]
    > O nome da tabela deve estar listado na tabela na seção [Definir a configuração do aplicativo](#configure-the-application-setup), descrita anteriormente neste tópico.

5. Selecione o nome do campo na tabela a ser consultada.
6. Insira o nome da tabela e o nome do campo para os critérios de consulta.
7. Repita as etapas 5 e 6 para adicionar mais campos e critérios à consulta e selecione **OK**.
8. Selecione **OK**.

## <a name="view-submission-logs"></a>Exibir logs de envio

1. Acesse **Administração da organização** \> **Periódico** \> **Documentos eletrônicos** \> **Log de envio de documentos eletrônicos**.
2. No campo **Tipo de documento**, selecione a tabela que contém as faturas.

    > [!NOTE]
    > O nome da tabela deve estar listado na tabela na seção [Definir a configuração do aplicativo](#configure-the-application-setup), descrita anteriormente neste tópico.

3. Selecione uma fatura na grade e, depois, selecione **Consultar** \> **Detalhes de envio**.


## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral do Faturamento eletrônico](e-invoicing-service-overview.md)
- [Introdução à administração de serviço do Faturamento eletrônico](e-invoicing-get-started-service-administration.md)
- [Introdução ao Faturamento eletrônico para o Brasil](e-invoicing-bra-get-started.md)
- [Introdução ao Faturamento eletrônico para o México](e-invoicing-mex-get-started.md)
- [Introdução ao Faturamento eletrônico para a Itália](e-invoicing-ita-get-started.md)
- [Faturas eletrônicas do cliente no Egito](emea-egy-e-invoices.md)
- [Faturas eletrônicas do cliente na Arábia Saudita](emea-sau-e-invoices.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
