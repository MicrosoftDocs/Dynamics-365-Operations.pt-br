---
title: Limpeza de migração ER
description: Este tópico explica como você pode usar a função de limpeza de migração ER para resolver problemas com modelos ER.
author: NickSelin
ms.date: 04/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, ERParameters, ERMigrationCleanup
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 97dbb625fc312548fb266b2ef6643a2b8e2b0f81
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750877"
---
# <a name="er-migration-cleanup"></a>Limpeza de migração ER 

[!include[banner](../includes/banner.md)]

Quando você gerencia as instâncias do Finance, pode decidir migrar sua instância atual para outro local. Por exemplo, você poderá migrar sua instância de produção para um novo do ambiente de área restrita. Se você configurou a estrutura de Relatório eletrônico (ER) para armazenar modelos no Armazenamento de Blob Microsoft Azure, a tabela **DocuValue** no novo ambiente de área restrita refere-se à instância de Armazenamento de Blob no ambiente de produção. Entretanto, essa instância não pode ser acessada do ambiente de área restrita, pois o processo de migração não dá suporte à migração de artefatos no Armazenamento de Blob. Em vez disso, é esperado que no novo ambiente de área de armazenamento, você consulte a instância do armazenamento de Blob no ambiente de área restrita que ainda não obteve os modelos ER.

Se você tentar executar um formato de ER que usa um modelo para gerar documentos comerciais, ocorrerá uma exceção, e você será notificado sobre o modelo ausente. Você também é orientado a usar a opção de limpeza de migração ER para excluir e depois reimportar a configuração de formato de ER que contém o modelo.

[![Executando um formato ER](./media/er-migration-cleanup-run.png)](./media/er-migration-cleanup-run.png)

Você receberá um erro semelhante se navegar até a página **Configurações** (**Administração da organização** \> **Relatório eletrônico** \> **Configurações**) e na árvore de configurações, tente excluir uma configuração de formato ER que usa um modelo.

[![Exclusão um formato ER](./media/er-migration-cleanup-delete.png)](./media/er-migration-cleanup-delete.png)

Conclua as etapas a seguir para solucionar problemas com modelos ER que não podem ser acessados.

1.  Vá para a página **Administração da organização** \> **Periódico** \> **Limpeza de migração**.
2.  Selecione uma configuração de formato ER que não pode ser executada ou excluída.
3.  Selecione **Excluir**.
4.  Confirme a exclusão da configuração de formato ER selecionado.
5.  [Importar](download-electronic-reporting-configuration-lcs.md) a configuração de formato ER excluído para a instância Finance atual.

## <a name="applicability"></a>Aplicabilidade

> [Importante] A opção **Limpeza de migração** destina-se apenas a configurações de formato ER que contêm modelos ER não acessíveis. Quando você exclui uma configuração de formato ER usando a opção **Limpeza de migração**, o ER exclui os modelos relacionados aos artefatos de configuração no único banco de dados de aplicativo. A existência dos arquivos físicos apropriados no armazenamento de Blob não é validada. Em vez disso, pressupõe-se que não há nenhum. Portanto, não use a opção **Limpeza de migração** como uma alternativa para a opção de exclusão da configuração ER na página **Configurações**. Use a opção **Limpeza de migração** apenas quando uma opção de exclusão da configuração ER na página **Configurações** falhar.
>
> Se você usar a opção **Limpeza de migração** para excluir uma configuração de formato ER quando o modelo conhecido está disponível no armazenamento do Blob, você exclui somente artefatos de configuração relacionados no banco de dados do aplicativo. O arquivo físico do modelo no armazenamento de Blob permanece. Não é mais permitido substituir o arquivo no armazenamento de Blob. Para obter mais informações, consulte [KB4557217](https://fix.lcs.dynamics.com/Issue/Details?kb=4557217). Além disso, não será mais possível importar novamente as configurações excluídas usando a limpeza da migração neste ambiente. Para resolver esse problema, você precisa encontrar o arquivo correspondente no armazenamento Blob e excluí-lo manualmente.

[![Importação de um formato ER](./media/er-migration-cleanup-import.png)](./media/er-migration-cleanup-import.png)

Um problema semelhante pode ocorrer se você migrar sua instância do aplicativo para outro local que foi usado como um destino de migração mais de uma vez e para o qual o armazenamento de Blob já contém arquivos de modelo ER.

Como você pode ter várias configurações de formato de ER, esse processo pode ser demorado. Portanto, o uso do recurso [Armazenamento de backup do modelo ER](er-backup-storage-templates.md) para recuperar automaticamente os modelos com referências quebradas é preferível.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]