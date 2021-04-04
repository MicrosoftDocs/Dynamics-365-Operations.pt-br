---
title: Armazenamento em backup de modelos de ER
description: Este tópico explica como usar o armazenamento de backup de relatórios eletrônicos (ER) para a recuperação de modelos.
author: NickSelin
manager: AnnBe
ms.date: 04/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-08-13
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d1bf2f13833b4441812b1c5326f897415c752091
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565616"
---
# <a name="backup-storage-of-er-templates"></a>Armazenamento em backup de modelos de ER

[!include [banner](../includes/banner.md)]

A [Visão geral de ER (Relatórios eletrônicos)](general-electronic-reporting.md) permite que usuários comerciais configurem formatos para documentos de saída de acordo com os requisitos legais de vários países e regiões. Os formatos de ER configurados podem usar modelos predefinidos para gerar documentos de saída em vários formatos, como pastas de trabalho do Microsoft Excel, documentos do Microsoft Word ou documentos em PDF. Os modelos são preenchidos com os dados exigidos pelo fluxo de dados configurado para os documentos gerados.

Cada formato configurado pode ser publicado como parte de uma solução de ER. Cada solução de ER pode ser exportada de uma instância do Finance and Operations e importada para outra instância.

A estrutura de ER usa [Configurar gerenciamento de documentos](../../fin-ops/organization-administration/configure-document-management.md) para manter os modelos exigidos para a instância atual do Finance and Operations. Dependendo das configurações da estrutura de ER, o Armazenamento de Blob do Microsoft Azure ou uma pasta do Microsoft SharePoint podem ser selecionados como o local de armazenamento físico principal de modelos. Para obter mais informações, consulte [Configurar a estrutura de ER (Relatórios eletrônicos)](electronic-reporting-er-configure-parameters.md). A tabela DocuValue mantém um registro individual para cada modelo. Em cada registro, o campo **AccessInformation** armazena o caminho de um arquivo de modelo que encontra-se no local de armazenamento configurado.

Quando você gerencia as instâncias do Finance and Operations, pode decidir migrar a instância atual para outro local. Por exemplo, você poderá migrar sua instância de produção para um novo do ambiente de área restrita. Se você configurou a estrutura de ER para armazenar modelos no Armazenamento de Blob, a tabela DocuValue no novo ambiente de área restrita refere-se à instância de Armazenamento de Blob no ambiente de produção. Entretanto, essa instância não pode ser acessada do ambiente de área restrita, pois o processo de migração não dá suporte à migração de artefatos no Armazenamento de Blob. Portanto, se você tentar executar um formato de ER que usa um modelo para gerar documentos comerciais, ocorrerá uma exceção, e você será notificado sobre o modelo ausente. Você também é orientado a usar a ferramenta de limpeza de ER para excluir e depois reimportar a configuração de formato de ER que contém o modelo. Como você pode ter várias configurações de formato de ER, esse processo pode ser demorado.

O recurso de armazenamento de backup de modelos de ER pode ajudar a produzir seus modelos de modo que estejam sempre disponíveis para gerar documentos comerciais.

> [!NOTE]
> Esse recurso pode ser usado somente quando o Armazenamento de Blob foi selecionado como local de armazenamento físico de modelos de ER.

## <a name="automated-recovery-and-notification"></a>Recuperação e notificação automatizadas

Para esse recurso, cada modelo de uma nova configuração de formato de ER no ambiente atual é salvo automaticamente no local de armazenamento de backup de modelos (a tabela de banco de dados ERDocuDatabaseStorage) quando ocorrem os seguintes eventos:

- Você importa uma nova configuração de formato de ER que contém um modelo.
- Você conclui a versão de rascunho de uma configuração de formato de ER que contém um modelo.

Cópias de backup de modelos são migradas para uma nova instância do Finance and Operations como parte do banco de dados do aplicativo.

Se um modelo de um formato de ER for necessário para a geração de documentos de saída, processar pagamentos de fornecedor, inclusive a geração de avisos de pagamento e relatórios de controle, por exemplo, mas o modelo necessário não se encontra no local de armazenamento principal, os seguintes eventos ocorrerão:

- Se o modelo estiver disponível no local de armazenamento de backup, ele será obtido automaticamente do local de armazenamento de backup, restaurado no local de armazenamento principal e usado para a execução atual.
- Cada usuário com a função **Desenvolvedor de relatório eletrônico** ou **Administrador do sistema** atribuída é notificado sobre o problema de modelo ausente por meio da Central de ações. A mensagem exibida depende do valor do parâmetro **Executar automaticamente o procedimento de restauração de modelos corrompidos em lotes**:

    - Se esse parâmetro estiver definido como **Desativado**, a mensagem recomendará que você inicie o processo em lote para corrigir automaticamente problemas semelhantes de outros modelos de configuração de formato de ER. A mensagem inclui um link que você pode usar para iniciar o processo em lote.
    - Se esse parâmetro estiver definido como **Ativado**, a mensagem o notificará de que foi identificado um problema de modelos ausentes e que um novo processo em lote, **Restaurar modelos corrompidos do backup do banco de dados interno**, será agendado automaticamente. Esse processo em lote corrigirá automaticamente problemas semelhantes de outros modelos.

Para configurar o parâmetro **Executar automaticamente o procedimento de restauração de modelos corrompidos em lotes**, siga estas etapas:

1. No Finance and Operations, abra a página **Administração da organização \> Relatório eletrônico \> Configurações**.
2. Na página **Configurações**, no Painel Ação, na guia **Configurações**, no grupo **Configurações avançadas**, selecione **Parâmetros de usuário**.
3. Na caixa de diálogo **Parâmetros de usuário**, defina o valor necessário para o parâmetro **Executar automaticamente o procedimento de restauração de modelos corrompidos em lotes** .

> [!NOTE]
> Esse parâmetro é definido como específico da empresa registrada e do usuário do aplicativo.

![Página de configurações de ER](./media/GER-BackupTemplates-1.png)

A ilustração a seguir mostra um exemplo da mensagem que aparece quando o parâmetro **Executar automaticamente o procedimento de restauração de modelos corrompidos em lotes** está definido como **Ativado**.

![Página do diário de pagamentos do fornecedor](./media/GER-BackupTemplates-2.png)

A ilustração a seguir mostra o processo em lote **Restaurar modelos corrompidos do backup do banco de dados interno** na página **Trabalho em lotes** .

![Página Trabalho em lotes](./media/GER-BackupTemplates-3.png)

O log de execução do processo em lote **Restaurar modelos corrompidos do backup do banco de dados interno** concluído inclui informações sobre os modelos que foram restaurados do local de armazenamento de backup para o local de armazenamento principal.

![Página Histórico de trabalho em lotes](./media/GER-BackupTemplates-4.png)

Por padrão, o processo de criação automática de cópias de backup de modelos que residem em configurações de formato de ER fica ativado. Para parar de fazer cópias de backup de modelos, defina a opção **Parar de fazer cópias de backup de modelos** como **Sim** na guia **Anexos** da página **Parâmetros de relatório eletrônico**. Você pode abrir essa página no espaço de trabalho **Relatório eletrônico**.

Se você definiu a opção **Parar de fazer backup cópias de modelos** como **Sim** e não deseja manter as cópias de backup de modelos feitas anteriormente, selecione **Limpar o armazenamento de backup** na página **Parâmetros de relatório eletrônico** .

Se você atualizou seu ambiente para o Finance and Operations versão 10.0.5 (outubro de 2019) e deseja migrar para um novo ambiente que inclui as configurações de formato de ER que podem ser executadas, selecione **Preencher o armazenamento de backup** na página **Parâmetros de relatório eletrônico** antes da migração. Esse botão inicia o processo de fazer cópias de backup de todos os modelos disponíveis, de modo que elas possam ser armazenadas no local de armazenamento de backup de ER para modelos.

![Página de parâmetros de relatórios eletrônicos](./media/GER-BackupTemplates-5.png)

## <a name="manual-recovery"></a>Recuperação manual

Vá para **Administração da organização** \> **Relatório eletrônico** \> **Restaurar modelos desfeitos** para iniciar manualmente o processo de restaurar modelos de ER do local de armazenamento de backup para o local de armazenamento primário. Antes de iniciar este processo, na página **Restaurar modelos desfeitos**, é possível especificar se ele será executado de forma interativa ou se o processo em lote será agendado para isso.

## <a name="supported-deployments"></a>Implantações com suporte

No Finance and Operations versão 10.0.5, o recurso de armazenamento em backup de modelos de ER está disponível somente em implantações de nuvem.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de Relatório eletrônico (ER)](general-electronic-reporting.md)

[Configurar a estrutura de ER (Relatórios eletrônicos)](electronic-reporting-er-configure-parameters.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]