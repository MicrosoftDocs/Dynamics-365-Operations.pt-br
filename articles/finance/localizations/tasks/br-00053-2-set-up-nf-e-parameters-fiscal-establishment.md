---
title: Configurar parâmetros de NF-e para um estabelecimento fiscal (Brasil)
description: Use o procedimento a seguir para configurar os parâmetros para uma Nota Fiscal eletrônica (NF-e) e para um estabelecimento fiscal.
author: sndray
manager: AnnBe
ms.date: 06/26/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7008122636af0dddb72d6d7ba13416de8bc43cc0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4975297"
---
# <a name="set-up-nf-e-parameters-for-a-fiscal-establishment-brazil"></a>Configurar parâmetros de NF-e para um estabelecimento fiscal (Brasil)

[!include [banner](../../includes/banner.md)]

Use o procedimento a seguir para configurar os parâmetros para uma Nota Fiscal eletrônica (NF-e) e para um estabelecimento fiscal. Esta tarefa usa a empresa de demonstração BRMF.

1. Vá para Administração da organização > Organizações > Estabelecimentos fiscais > Estabelecimentos fiscais.
2. Selecione um estabelecimento fiscal para o qual será configurada a NF-e.
3. Expanda a seção NF-e e NFC-e federal.
4. Clique em Editar.
5. Insira o certificado digital que autentica os documentos eletrônicos fiscais que são emitidos pelo estabelecimento fiscal.
6. Selecione o tipo do ambiente da NF-e.
    * Selecione Testes para emitir NF-e para um ambiente de teste. Selecione Produção para emitir uma NF-e válida para o ambiente de produção da autoridade do imposto.  
7. Selecione a versão do esquema XML da NF-e.
8. Selecione a autoridade da UF da NF-e.
9. Selecione o modelo de email padrão que deve ser usado para notificar o cliente quando a NF-e for autorizada pela autoridade fiscal.
10. Selecione o modelo de email padrão que deve ser usado para notificar o cliente quando a NF-e for cancelada pela autoridade fiscal.
11. Selecione o modelo de email padrão que deve ser usado para notificar o cliente quando a NF-e for atualizada por uma carta de correção eletrônica.
12. Selecionar Sim no campo do formulário pré-impresso de segurança.
    * Selecione esta opção quando o estabelecimento fiscal usar o formulário pré-impresso de segurança para imprimir o DANFE em modo de contingência de formulário de segurança.  
13. Selecione Sim no campo Anexar DANFE em PDF ao email.
    * Selecione esta opção para anexar automaticamente o DANFE ao email que é enviado ao cliente após a NF-e ser autorizado pela autoridade fiscal.  
14. Selecione Sim no campo Imprimir DANFE quando NF-e for aprovada.
    * Selecione esta opção para imprimir o DANFE automaticamente após a NF-e ser autorizada pela autoridade fiscal.  
15. Selecione Sim no campo Validar esquema XML no lançamento.
    * Selecione esta opção para validar o XML de NF-e com o esquema XML oficial que é publicado pela autoridade fiscal antes de as notas serem lançadas.  
16. Selecionar Sim no campo Lançar somente NF-e com chave de acesso validada.
    * Selecione esta opção para validar a chave de acesso de NF-e de uma NF-e um que é emitida por um fornecedor antes que as notas fiscais do fornecedor sejam lançadas.  
17. Selecione Sim no campo Não postar NF-e se o XML não corresponder com a fatura.
    * Selecione esta opção se uma nota fiscal de fornecedor não tiver que ser lançada se o XML de NF-e de fornecedor não corresponder à ordem.  
18. Clique em Salvar.
19. Feche a página.

