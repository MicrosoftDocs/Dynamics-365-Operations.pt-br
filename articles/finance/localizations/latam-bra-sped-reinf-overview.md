---
title: SPED-Reinf (Brasil)
description: Este artigo fornece informações sobre como usar os Livros fiscais e a estrutura de mensagem eletrônica para configurar eventos do SPED-Reinf.
author: AdamTrukawka
ms.date: 04/09/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: atrukawk
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8.0999999999999996
ms.search.form: ''
ms.openlocfilehash: ef840a75e9aa39b1e46ba9fd63e761a0a48a60c4
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272105"
---
# <a name="sped-reinf-brazil"></a>SPED-Reinf (Brasil) 

[!include [banner](../includes/banner.md)]

O SPED-Reinf é um relatório de declaração de imposto que reúne informações sobre retenção de impostos e outras informações fiscais da Receita Federal do Brasil (RFB) e do Seguro Social. Em português do Brasil, a abreviação *Reinf* representa "retenções e outras informações fiscais". O SPED-Reinf foi criado para acessar taxas federais que são retidas para fins de Seguro Social e impostos de renda, bem como para atividades que não sejam relacionadas ao trabalho. Exemplos dessas atividades incluem documentos fiscais e pagamentos.  

A declaração consiste em um grupo de eventos. Esses eventos devem ser entregues em layouts específicos por meio do sistema de registro digital público (SPED), e um certificado digital válido deve ser usado para entregá-los. Este certificado pode ser emitido por uma entidade que foi creditada pela Infraestrutura de chave pública do (ICP-Brasil).

A declaração é considerada válida depois que o recebimento é confirmado e o conteúdo dos arquivos é validado.

O Microsoft Dynamics 365 Finance permite a geração de eventos do SPED-Reinf por meio do módulo **Livros fiscais** e a estrutura de registro de relatórios Provisionamento imediato de informações (SII). Você pode trocar mensagens XML para cada evento que a autoridade fiscal exigir.

## <a name="support-scope"></a>Escopo de suporte

- **Versões do SPED-Reinf com suporte:** 1.4 e 1.5.1.
- **Versões de produto com suporte:** Microsoft Dynamics AX 2012 R3 e Dynamics 365 Finance.
- A procuração eletrônica não tem suporte.

## <a name="table-of-events"></a>Tabela de eventos

| Evento | descrição | Tipo de evento | Suportado |
|---|---|---|---|
| R-1000 | Informações do contribuinte | Inicial | Sim |
| R-1070 | Processo administrativo e judicial | Quando um processo está em vigor | Sim |
| R-2010 | Serviços adquiridos | Evento periódico | Sim |
| R-2020 | Serviços fornecidos | Evento periódico | Sim |
| R-2030 | Valores recebidos por associações esportivas | Evento periódico | Não |
| R-2040 | Valores pagos a associações esportivas | Evento periódico | Não |
| R-2050 | Comércio da produção rural por entidades legais rurais ou pelo agronegócio | Evento periódico | Não |
| R-2055 | Aquisição de fornecedor agrícola | Evento periódico | Sim |
| R-2060 | Apuração do INSS-CPRB | Evento periódico | Sim |
| R-2098 | Reabertura de atividades periódicas | Evento periódico | Sim |
| R-2099 | Fechamento | Evento periódico | Sim |
| R-3010 | Receita de eventos esportivos | Evento não periódico | Não |
| R-5001 | Base de cálculo de impostos consolidada por contribuinte | Evento não periódico | Não |
| R-5011 | Base consolidada e valor do imposto | Evento não periódico | Sim |
| R-9000 | Exclusão | Evento não periódico | Sim |

> [!NOTE]
> Os eventos R-2010 e R-2020 são permitidos para o Cadastro Nacional de Pessoas Jurídicas (CNPJ) de terceiros. O evento R-5011 é usado para consultar o status do evento de fechamento R-2099.

Somente os contribuintes em conformidade com o SPED-ECD têm suporte.

- Não há suporte para contribuintes como departamentos públicos.
- Não há suporte para os serviços fornecidos em projetos de construção civil.
- Não há suporte para consumidores de serviços em projetos de construção civil.
- O registro manual é obrigatório para o pagamento de liquidação da contribuição do Seguro Social sobre o valor da receita bruta (CPRB) que é devido.
- O pagamento do valor CPRB que é devido está fora do escopo.

Para gerar e enviar os eventos relacionados à autoridade fiscal, siga estas etapas.

1. [Configure a funcionalidade de mensagem eletrônica](latam-bra-sped-reinf-electronic-messages.md). 
2. [Configure os livros fiscais](latam-bra-sped-reinf-setup-fiscal-books.md).
3. [Processe e envie os eventos](latam-bra-sped-reinf.md).
