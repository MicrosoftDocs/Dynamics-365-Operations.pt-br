---
title: Introdução ao complemento de faturamento eletrônico
description: Este tópico fornece informações que ajudarão você a começar a usar o complemento de faturamento eletrônico no Microsoft Dynamics 365 Finance e no Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 02/22/2021
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
ms.openlocfilehash: 56227e031f8205836bcae9ce26006fc8091c2863
ms.sourcegitcommit: 543772ee97efe215cf6f2ec6e092cc1568919f20
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/13/2021
ms.locfileid: "5592541"
---
# <a name="get-started-with-the-electronic-invoicing-add-on"></a>Introdução ao complemento de faturamento eletrônico

[!include [banner](../includes/banner.md)]

Este tópico fornece informações que ajudarão você a começar a usar o complemento de faturamento eletrônico.

A tabela a seguir lista os recursos de faturamento eletrônico e os documentos comerciais aos quais eles podem ser aplicados.

| Nome do recurso                         | Documento comercial |
|--------------------------------------|-------------------|
| Faturas eletrônicas austríacas (AT)    | <p>Fatura de venda</p><p>Fatura de projeto</p> |
| Fatura eletrônica belga (BE)      | <p>Fatura de venda</p><p>Fatura de projeto</p> |
| NF-e brasileira (BR)                  | <p>Modelo de nota fiscal 55</p><p>Carta de correção</p> |
| NFS-e ABRASF Curitiba brasileira (BR) | Documento fiscal de serviço |
| Fatura eletrônica dinamarquesa (DK)       | <p>Fatura de venda</p><p>Fatura de projeto</p> |
| Fatura eletrônica egípcia (EG)     | <p>Fatura de venda</p><p>Fatura de projeto</p> |
| Fatura eletrônica estoniana (EE)     | <p>Fatura de venda</p><p>Fatura de projeto</p> |
| Fatura eletrônica finlandesa (FI)       | <p>Fatura de venda</p><p>Fatura de projeto</p> |
| Fatura eletrônica francesa (FR)       | <p>Fatura de venda</p><p>Fatura de projeto</p> |
| Fatura eletrônica alemã (DE)       | <p>Fatura de venda</p><p>Fatura de projeto</p> |
| FatturaPA (IT)                       | <p>Fatura de venda</p><p>Fatura de projeto</p> |
| CFDI Interfactura mexicana (MX)       | <p>Fatura de venda</p><p>Guia de Remessa</p><p>Transferência de estoque</p><p>Complemento de pagamento</p> |
| Fatura eletrônica holandesa (NL)        | <p>Fatura de venda</p><p>Fatura de projeto</p> |
| Fatura eletrônica norueguesa (NO)    | <p>Fatura de venda</p><p>Fatura de projeto</p> |
| Fatura eletrônica espanhola (ES)      | <p>Fatura de venda</p><p>Fatura de projeto</p> |
| Fatura eletrônica PEPPOL            | <p>Fatura de venda</p><p>Fatura de projeto</p> |

## <a name="prerequisites"></a>Pré-requisitos

Antes de concluir os procedimentos neste tópico, é preciso ter os seguintes pré-requisitos em vigor:

- Configure o RCS (serviço de configuração regulatória) e o ambiente do Microsoft Dynamics 365 Finance ou Dynamics 365 Supply Chain Management para que você possa enviar ao complemento do faturamento eletrônico.
- Crie um ambiente de serviço e publique-o no complemento de faturamento eletrônico. Para obter mais informações, consulte [introdução à administração do serviço de complemento de faturamento eletrônico](e-invoicing-get-started-service-administration.md).
- Crie um aplicativo conectado. Para obter mais informações, consulte [introdução à administração do serviço de complemento de faturamento eletrônico](e-invoicing-get-started-service-administration.md).
- Crie um provedor de configuração para sua organização. Para obter mais informações, consulte [Criar provedor de configuração e marcá-lo como ativo](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider"></a>Importar um recurso de faturamento eletrônico do provedor de configuração da Microsoft 

1. Entre na conta RCS (serviço de configuração regulatória).
2. No espaço de trabalho **Recurso de globalização**, na seção **Recursos**, selecione o bloco **Complemento de faturamento eletrônico**.
3. Selecione **Importar** e, em seguida, **Sincronizar**.
4. Filtre a coluna **Provedor de configuração** pelo termo **Microsoft**.
5. Selecione o nome de um recurso de faturamento eletrônico na tabela no início deste tópico e selecione **Importar**.

## <a name="create-an-electronic-invoicing-feature-under-your-organization-provider"></a>Crie um recurso Faturamento eletrônico para o provedor da sua organização

1. No RCS, na seção **Recursos** do espaço de trabalho **Recurso de globalização**, selecione o bloco **Complemento Faturamento eletrônico**.
2. Selecione **Adicionar** > **Baseado em recurso existente** e, no campo **Nome**, insira o nome do recurso de faturamento eletrônico.
3. No campo **Descrição**, insira uma descrição do recurso.
4. No campo **Recurso base**, selecione o recurso de faturamento eletrônico importado do provedor de configuração da Microsoft.
5. Selecione **Criar recurso**.

## <a name="configure-the-electronic-invoicing-feature"></a>Configurar o recurso de faturamento eletrônico

Dependendo do país ou da região, o recurso de faturamento eletrônico pode exigir configuração adicional. 

Para obter as etapas específicas, consulte a documentação "Introdução" que está disponível para seu país ou região.

## <a name="configure-the-application-setup"></a>Definir a configuração do aplicativo

1. Selecione o recurso de faturamento eletrônico criado por você.
2. Na guia **Versão**, verifique se a versão de **Rascunho** está selecionada.
3. Na guia **Configurações**, selecione **Configuração do aplicativo**.

    > [!NOTE]
    > Verifique se a sua organização está definida como o provedor de configuração **Ativo**. Para obter mais informações, consulte [Criar provedor de configuração e marcá-lo como ativo.](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

4. Selecione **Configuração do recurso** e, depois, **Aplicativo conectado**.
5. Na seção **Tipos de documento eletrônico**, selecione **Adicionar**.
6. Para cada documento comercial com suporte do recurso, selecione e insira um valor **Nome de tabela** de acordo com a tabela a seguir.

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
    | Fatura eletrônica PEPPOL            | <p>Fatura de venda</p><p>Fatura de projeto</p> | <p>Diário de faturas de clientes</p><p>Fatura de projeto</p> |

7. Para cada documento comercial com suporte do recurso, selecione e insira um valor **Contexto** de acordo com a tabela a seguir.

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

8. Para cada documento comercial com suporte do recurso, selecione e insira um valor **Mapeamento de documento comercial** de acordo com a tabela a seguir.

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

Dependendo do país ou da região, o recurso de faturamento eletrônico pode exigir configuração adicional.

Para obter etapas específicas, consulte a documentação "Introdução" que está disponível para seu país ou região.

## <a name="deploy-the-electronic-invoicing-feature"></a>Implantar o recurso de faturamento eletrônico

1. Na guia **Versões**, selecione a versão do recurso de faturamento eletrônico que você deseja implantar.
2. Selecione **Alterar status** \> **Concluir**.
3. Selecione **Alterar status** \> **Publicar**.
4. Selecione **Implantar**.
5. Defina a opção **Implantar para aplicativo conectado** como **Sim**.
6. Na página **Conectar aplicativo**, selecione a conexão que está associada à sua instância do Finance ou Supply Chain Management.
7. Defina a opção **Implantar para ambiente de serviço** como **Sim**.
8. No campo **Ambiente de serviço**, selecione o ambiente do serviço de complemento de faturamento eletrônico em que você deseja implantar o recurso de faturamento eletrônico.
9. No campo **Data Inicial**, selecione a data em que o recurso de faturamento eletrônico deve se tornar efetivo no complemento de faturamento eletrônico.
10. Selecione **OK**.

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

4. Selecione **Salvar**.

## <a name="issue-electronic-invoices"></a>Emitir faturas eletrônicas

1. Vá para **Administração da organização** \> **Periódico** \> **Documentos eletrônicos** \> **Enviar documentos eletrônicos**.
2. Na FastTab **Registros a serem incluídos**, selecione **Filtro**.
3. Selecione **Adicionar** para adicionar um nome de tabela ao filtro de consulta.
4. Selecione a tabela que contém as faturas.

    > [!NOTE]
    > O nome da tabela deve estar listado na tabela na seção [Definir a configuração do aplicativo](#configure-the-application-setup), descrita anteriormente neste tópico.

5. Selecione o nome do campo na tabela a ser consultada.
6. Insira o nome da tabela e o nome do campo para os critérios de consulta.
7. Repita as etapas 5 e 6 para adicionar mais campos e critérios à consulta e selecione **OK**.
8. Selecione **OK**.

## <a name="view-submission-logs"></a>Exibir logs de envio

1. Vá para **Administração da organização** \> **Periódico** \> **Documentos eletrônicos** \> **Log de envio de documentos eletrônicos**.
2. No campo **Tipo de documento**, selecione a tabela que contém as faturas.

    > [!NOTE]
    > O nome da tabela deve estar listado na tabela na seção [Definir a configuração do aplicativo](#configure-the-application-setup), descrita anteriormente neste tópico.

3. Selecione uma fatura na grade e, depois, selecione **Consultar** \> **Detalhes de envio**.


## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral de faturamento eletrônico](e-invoicing-service-overview.md)
- [Introdução à administração de serviço do complemento do Faturamento eletrônico](e-invoicing-get-started-service-administration.md)
- [Introdução ao complemento de faturamento eletrônico para o Brasil](e-invoicing-bra-get-started.md)
- [Introdução ao complemento de faturamento eletrônico para o México](e-invoicing-mex-get-started.md)
- [Introdução ao complemento de faturamento eletrônico para a Itália](e-invoicing-ita-get-started.md)
- [Faturas eletrônicas do cliente no Egito](emea-egy-e-invoices.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
