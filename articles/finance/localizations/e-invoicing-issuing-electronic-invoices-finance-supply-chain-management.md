---
title: Emitir faturas eletrônicas no Finance e no Supply Chain Management
description: Este tópico explica como emitir faturas eletrônicas no Microsoft Dynamics 365 Finance e no Dynamics 365 Supply Chain Management por meio do complemento de faturamento eletrônico.
author: gionoder
manager: AnnBe
ms.date: 01/28/2021
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
ms.openlocfilehash: 187f5a20d088b4fcd7af2a6576357a69c2efc2c6
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104344"
---
# <a name="issue-electronic-invoices-in-finance-and-supply-chain-management"></a>Emitir faturas eletrônicas no Finance e no Supply Chain Management

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Este tópico explica como emitir faturas eletrônicas no Microsoft Dynamics 365 Finance e no Dynamics 365 Supply Chain Management por meio do complemento de faturamento eletrônico.


## <a name="feature-activation"></a>Ativação de recurso

Para iniciar a emissão de faturas eletrônicas por meio do complemento do faturamento eletrônico, é necessário ativar a referência do recurso no Finance e no Supply Chain Management.

Cada referência de recurso corresponde a um recurso de faturamento eletrônico específico que atende aos requisitos de faturamento eletrônico de um país/região.

A tabela a seguir mostra a lista de referências de recursos que têm suporte do complemento de faturamento eletrônico.

| Referência de recursos | Organização                                              | País/região |
|-------------------|---------------------------------------------------|----------------|
| BR-00053          | NF-e Federal - Fatura eletrônica brasileira       | Brasil         |
| BR-00095          | Faturas eletrônicas brasileiras NFS-e               | Brasil         |
| DK-00001          | Faturamento eletrônico para o setor público (OIOUBL) – DK    | Dinamarca        |
| EG-00008          | Faturamento eletrônico para o Egito                             | Egito          |
| ES-00025          | Fatura eletrônica para o setor público           | Espanha          |
| EUR-00023         | Faturamento eletrônico da União Europeia para o setor público       | Europa         |
| ITA-00036         | IT - Faturamento eletrônico para o setor público (FatturaPA) | Itália          |
| MX-00010          | Faturamento eletrônico CFDI                                  | México         |
| MX-00016          | CFDI de faturamento eletrônico - processo de cancelamento           | México         |

Nos casos em que há um recurso de faturamento eletrônico herdado, com suporte ao escopo de localização de países, a ativação da referência do recurso permite a emissão de faturas eletrônicas por meio do complemento de faturamento eletrônico e desativa o antigo recurso.

## <a name="submit-electronic-documents"></a>Enviar documentos eletrônicos

O processo de envio de documentos eletrônicos representa o único ponto de comunicação entre o Finance e o Supply Chain Management e o complemento de faturamento eletrônico. Durante cada evento de envio, os fluxos de comunicação nas duas direções:

- **Do Finance e Supply Chain Management para o complemento de faturamento eletrônico** – o Finance e o Supply Chain Management enviam as faturas abstratas para o complemento de faturamento eletrônico. Conforme necessário, eles também enviam o conteúdo de variáveis que foram configuradas como parte dos recursos de faturamento eletrônico.
- **Do complemento de faturamento eletrônico para o Finance e o Supply Chain Management** – dependendo do recurso de faturamento eletrônico, o Finance e o Supply Chain Management recebem atualizações do complemento de faturamento eletrônico sobre os resultados de processamento de faturas que foram previamente enviadas. Eles também recebem o conteúdo de variáveis que foram configuradas como parte dos recursos de faturamento eletrônico.

Para enviar documentos eletrônicos para o complemento de faturamento eletrônico, no Finance e no Supply Chain Management, acesse **Administração da organização &gt; Periódico &gt; Documentos eletrônicos &gt; Enviar documentos eletrônicos**.

O ponto de partida é uma fatura lançada. Essa fatura pode ter origens diferentes, como ordens de venda, faturas de projeto ou faturas de texto livre.

O processo de envio pode ser executado manualmente ou em segundo plano.

- **Execução manual** – para execução manual, você deve usar a opção **Filtro** para definir o intervalo de documentos que devem ser enviados. Na página **Filtros**, você pode configurar sua própria consulta para selecionar as faturas lançadas que devem ser enviadas. Após a seleção, você deve iniciar manualmente a execução do processamento e esperar que ela seja concluída. Quando o processamento é concluído, uma mensagem na Central de ações mostra o número de documentos eletrônicos que foram enviados com êxito.
- **Execução em segundo plano** – a execução em segundo plano é executada sem exigir que você se conecte ou mantenha a caixa de diálogo de envio aberta. Você pode programar o processo para ser executado e definir a frequência de execução.

## <a name="view-the-submission-logs"></a>Exibir os logs de envio

No Finance e no Supply Chain Management, você pode usar os logs de envio para exibir os resultados do processamento do envio para o complemento de faturamento eletrônico. Acesse **Administração da organização &gt; Periódico &gt; Documentos eletrônicos &gt; Envio de documentos eletrônicos**. Depois, no campo **Tipo de documento**, selecione um valor para filtrar o tipo de faturas que os logs mostram.

Há três status de envio possíveis:

- **Agendado** – o complemento de faturamento eletrônico recebeu o envio do Finance e do Supply Chain Management, e o processamento do recurso de faturamento eletrônico está em andamento.
- **Concluído** – o complemento de faturamento eletrônico processou com êxito o recurso de faturamento eletrônico pois estava configurado para executá-lo.
- **Falha** – o complemento de faturamento eletrônico encontrou um erro ou foi interrompido por uma exceção durante o processamento do recurso de faturamento eletrônico.

> [!IMPORTANT]
> O status do envio se refere ao status do processamento que o complemento do faturamento eletrônico faz no recurso de faturamento eletrônico. Ele não se refere ao status final da própria fatura eletrônica.
>
> Por exemplo, se uma fatura eletrônica precisar ser enviada para um serviço Web externo para aprovação, o status de envio poderá ser **Concluído**, mas o status da fatura eletrônica poderá ser **Rejeitado**. Nesse caso, o complemento de faturamento eletrônico conseguiu processar com êxito o recurso de faturamento eletrônico pois estava configurado para processar esse recurso. No entanto, a fatura eletrônica foi rejeitada porque não atendeu aos critérios estabelecidos pelo serviço Web para a aprovação da fatura.

Os logs de envio incluem as seguintes funções adicionais:

- **Detalhes do envio** – exiba os detalhes do envio principal. A visualização mostra o log de execução completo das ações que são configuradas no recurso de faturamento eletrônico. Ela também permite que os usuários baixem os arquivos criados durante o processamento. Em cenários em que a fatura deve ser aprovada por um serviço Web externo, ela permite que os usuários exibam o status da fatura.
- **Envios relacionados** – exiba os detalhes de envios secundários.
- **Cancelar envios** – esta função habilita um processo de envio especial em cenários nos quais a fatura eletrônica deve ser aprovada por um serviço Web externo. Ela instrui o complemento de faturamento eletrônico a enviar ao serviço Web uma mensagem específica que pretende cancelar o status de uma fatura eletrônica aprovada no banco de dados do serviço Web.
- **Reenviar documento** – reenviar um documento eletrônico que já foi enviado ao complemento do faturamento eletrônico. Um log totalmente novo é criado na página **Detalhes do envio**.
- **Enviar envio relacionado**
