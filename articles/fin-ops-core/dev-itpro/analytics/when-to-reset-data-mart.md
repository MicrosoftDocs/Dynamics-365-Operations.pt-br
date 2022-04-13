---
title: Perguntas frequentes sobre redefinições do data mart
description: Este tópico fornece respostas a algumas perguntas frequentes sobre redefinições do data mart.
author: jinniew
ms.date: 03/21/2022
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
ms.openlocfilehash: ab6417a739e9a7b67b9e67d93f3bef654e55e5e4
ms.sourcegitcommit: 2c2ef3e312e7221006a9e230c9378bb4c1b4cd33
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2022
ms.locfileid: "8466401"
---
# <a name="data-mart-resets-faq"></a>Perguntas frequentes sobre redefinições do data mart

Este tópico fornece respostas a algumas perguntas frequentes sobre redefinições do data mart. Uma redefinição do data mart pode ser um processo demorado e, dependendo das circunstâncias, pode não ser a solução necessária. Portanto, este tópico inclui informações sobre as circunstâncias em que uma redefinição do data mart pode ajudar e também quando é improvável que isso ajude.

## <a name="what-is-a-data-mart-reset"></a>O que é uma redefinição de data mart?

Uma redefinição do data mart desativará as tarefas de integração, excluirá todos os dados do data mart e, em seguida, reativará a integração.

Para garantir que os dados antigos não sejam inseridos, uma redefinição do data mart só pode ser iniciada após a conclusão das tarefas existentes. Se você tentar redefinir o data mart antes que todas as tarefas sejam concluídas, você pode receber uma mensagem como: "A redefinição do data mart não pôde ser processada por causa de uma tarefa ativa. Tente novamente mais tarde."

## <a name="when-do-i-have-to-do-a-data-mart-reset"></a>Quando preciso fazer uma redefinição de data mart?

Se uma ou mais das seguintes declarações se aplicarem à sua situação, sua organização poderá se beneficiar de uma redefinição do data mart:

- **O banco de dados do aplicativo foi restaurado**
- **Você abriu um tíquete de suporte** – Um engenheiro de suporte orientou você a redefinir o data mart como parte de uma etapa de solução de problemas.
- **Grande porcentagem de registros obsoletos** – Os registros obsoletos por si só não justificam necessariamente uma redefinição de data mart. Altas porcentagens de dados obsoletos podem degradar a geração geral de relatórios e o desempenho da integração, além de aumentar o uso de espaço no banco de dados. É recomendável concluir uma redefinição do data mart para remover os dados obsoletos quando houver mais de 80% de dados obsoletos no data mart.
 
> [!NOTE]
> O processo de redefinição de um data mart é afetado pelo número da contabilidade e das transações de orçamento em seu banco de dados. Dependendo do número de transações no sistema, uma redefinição de data mart pode ser concluída em apenas 15 minutos, ou pode levar até quatro horas. No entanto, se a redefinição levar mais de quatro horas, recomendamos contatar o suporte.
 
## <a name="when-is-a-data-mart-reset-inappropriate"></a>Quando uma redefinição de um data mart é inadequada?

Veja algumas circunstâncias em que não é recomendável redefinir o data mart:

- Você está enfrentando problemas de desempenho da integração de dados.
- Sua integração do Financial Reporter não está habilitada. 

    - Isso significa que os dados da contabilidade não estão mais sincronizados com o data mart do Financial Reporting. Talvez o Financial Reporter não esteja obtendo números atualizados para seus relatórios financeiros. Isso normalmente ocorre se você passar um longo período sem usar o Financial Reporter.
    - Você será solicitado a habilitar a integração por meio da redefinição do data mart. Para continuar, selecione **Sim**. Você também pode optar por redefinir o data mart posteriormente. Depois que a integração for habilitada, os dados da contabilidade serão novamente sincronizados no Financial Reporter. 
- Você vê um padrão de redefinição recorrente por qualquer um dos seguintes motivos:

    - **Dados faltando ou inesperados no relatório** – Se você notar que há dados faltando, abra um tíquete de suporte com a Microsoft para analisar o formato do seu relatório e possíveis problemas de sincronização de dados.
    - **Estado de integração travado** – se você perceber que o status da integração está travado na execução, isso pode ser devido a um grande volume de transações no sistema. Este estado será resolvido sem intervenção. No entanto, se você perceber que o status de integração está travado por mais de quatro horas, abra um tíquete de suporte com a Microsoft. 
   
## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a>Se redefinir o data mart, perderei os relatórios já criados?

Não. Seus relatórios são armazenados em tabelas de SQL que não são afetadas por uma redefinição do data mart. Se estiver preocupado em perder os relatórios que criou, você poderá fazer backup daqueles que não deseja perder. Para fazer backups de projetos, abra o Report Designer e acesse **Empresa \> Empresas \> Blocos de construção \> Exportar**.
 
## <a name="do-all-users-have-to-exit-the-system-before-i-can-reset-the-data-mart"></a>Todos os usuários têm que sair do sistema antes que eu possa redefinir o data mart?

Não. Os usuários podem continuar trabalhando no sistema durante a redefinição do data mart. Porém, eles não poderão acessar os relatórios criados com o Financial Reporter até que a redefinição seja concluída.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
