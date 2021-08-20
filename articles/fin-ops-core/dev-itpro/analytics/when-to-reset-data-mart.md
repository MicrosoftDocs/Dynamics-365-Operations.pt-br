---
title: Perguntas frequentes sobre redefinições do data mart
description: Este tópico fornece respostas a algumas perguntas frequentes sobre redefinições do data mart.
author: jinniew
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-05-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: e5a40342306eb9888b456a865ab2220dccfe65f8ccecc67bf8fc16f907e06977
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6767746"
---
# <a name="data-mart-resets-faq"></a>Perguntas frequentes sobre redefinições do data mart

Este tópico fornece respostas a algumas perguntas frequentes sobre redefinições do data mart. Uma redefinição do data mart pode ser um processo demorado e, dependendo das circunstâncias, pode não ser a solução necessária. Portanto, este tópico inclui informações sobre as circunstâncias em que uma redefinição do data mart pode ajudar e também quando é improvável que isso ajude.

## <a name="what-is-a-data-mart-reset"></a>O que é uma redefinição de data mart?

Uma redefinição do data mart desativará as tarefas de integração, excluirá todos os dados do data mart e, em seguida, reativará a integração.

Para garantir que os dados antigos não sejam inseridos, uma redefinição do data mart só pode ser iniciada após a conclusão das tarefas existentes. Se você tentar redefinir o data mart antes que todas as tarefas sejam concluídas, você pode receber uma mensagem como: "A redefinição do data mart não pôde ser processada por causa de uma tarefa ativa. Tente novamente mais tarde."

## <a name="when-do-i-have-to-do-a-data-mart-reset"></a>Quando preciso fazer uma redefinição de data mart?

Se uma ou mais das seguintes declarações se aplicarem à sua situação, sua organização poderá se beneficiar de uma redefinição do data mart:

- O banco de dados do aplicativo foi restaurado.
- Você abriu um tíquete de suporte e foi orientado por um engenheiro de suporte a redefinir o data mart como parte de uma etapa de solução de problemas.
 
> [!NOTE]
> O processo de redefinição de um data mart é afetado pelo número da contabilidade e das transações de orçamento em seu banco de dados. Dependendo do número de transações no sistema, uma redefinição de data mart pode ser concluída em apenas 15 minutos, ou pode levar até quatro horas. No entanto, se a redefinição levar mais de quatro horas, recomendamos contatar o suporte.
 
## <a name="when-is-a-data-mart-reset-inappropriate"></a>Quando uma redefinição de um data mart é inadequada?

Veja algumas circunstâncias em que não é recomendável redefinir o data mart:

- Você está enfrentando problemas de desempenho associados a uma sincronização de dados.
- Você vê um padrão de redefinição recorrente por qualquer um dos seguintes motivos:

    - **Dados ausentes** – Se você notar que há dados faltando, abra um tíquete de suporte com a Microsoft para analisar o formato do seu relatório e possíveis problemas de sincronização de dados.
    - **Estado de integração travado**
    - **Registros obsoletos** – Os registros obsoletos por si só não justificam necessariamente uma redefinição de data mart. Se você tiver um grande conjunto de dados, o processo de redefinição levará algum tempo para ser executado, mas é improvável que isso resulte em melhorias.

## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a>Se redefinir o data mart, perderei os relatórios já criados?

Não. Seus relatórios são armazenados em tabelas de SQL que não são afetadas por uma redefinição do data mart. Se estiver preocupado em perder os relatórios que criou, você poderá fazer backup daqueles que não deseja perder. Para fazer backups de projetos, abra o Report Designer e acesse **Empresa \> Empresas \> Blocos de construção \> Exportar**.
 
## <a name="do-all-users-have-to-exit-the-system-before-i-can-reset-the-data-mart"></a>Todos os usuários têm que sair do sistema antes que eu possa redefinir o data mart?

Não. Os usuários podem continuar trabalhando no sistema durante a redefinição do data mart. Porém, eles não poderão acessar os relatórios criados com o Financial Reporter até que a redefinição seja concluída.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
