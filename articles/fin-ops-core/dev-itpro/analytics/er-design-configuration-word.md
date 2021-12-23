---
title: Criar uma nova configuração de (ER) para gerar relatórios no formato Word
description: Este tópico explica como os usuários podem configurar um novo formato de relatório eletrônico (ER) para gerar relatórios como documentos do Microsoft Word.
author: NickSelin
ms.date: 12/17/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner,  LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: Version 10.0.6
ms.openlocfilehash: 98d28c39b2923afecc851299a07aa3b93ef2edce
ms.sourcegitcommit: ac23a0a1f0cc16409aab629fba97dac281cdfafb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/29/2021
ms.locfileid: "7867285"
---
# <a name="design-a-new-er-configuration-to-generate-reports-in-word-format"></a>Criar uma nova configuração de (ER) para gerar relatórios no formato Word

[!include [banner](../includes/banner.md)]

Para gerar relatórios como documentos do Microsoft Word, você deve criar um modelo para os relatórios usando, por exemplo, o aplicativo da área de trabalho Word. A ilustração a seguir mostra o modelo de exemplo para o relatório de controle que pode ser gerado para mostrar detalhes de pagamentos de fornecedor processados.

![Modelo de exemplo para o relatório de controle no aplicativo da área de trabalho Word.](./media/er-design-configuration-word-image1.png)

Para usar um documento do Word como modelo para relatórios no formato Word, você pode configurar uma nova [solução](general-electronic-reporting.md) de [relatório eletrônico (ER)](er-quick-start1-new-solution.md). Esta solução deve incluir uma [configuração de ER](general-electronic-reporting.md#Configuration) que contenha um componente de [formato](general-electronic-reporting.md#FormatComponentOutbound) de ER.

> [!NOTE]
> Ao criar uma nova configuração de formato de ER para gerar relatórios no formato Word, você deve selecionar **Word** como o tipo formato na caixa de diálogo de **Criar configuração** ou deixar o campo **Tipo de formato** em branco.

![Criar uma configuração de formato na página Configurações.](./media/er-design-configuration-word-image2.gif)

O componente de formato de ER da solução deve conter o elemento de formato **Excel\\File**, e esse elemento de formato deve estar vinculado ao documento do Word que será usado como modelo para relatórios gerados no tempo de execução. Para configurar o componente de formato de ER, é necessário abrir a versão de [rascunho](general-electronic-reporting.md#component-versioning) da configuração de ER criada no designer de formato de ER. Em seguida, adicione o elemento **Excel\\File**, anexe seu modelo do Word ao formato de ER editável e vincule esse modelo ao elemento **Excel\\File** que você adicionou.

> [!NOTE]
> Ao anexar um modelo, você deve usar um [tipo de documento](../../fin-ops/organization-administration/configure-document-management.md#configure-document-types) que tenha sido [configurado](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) nos parâmetros de ER para armazenar modelos de formatos de ER.

![Anexar um modelo na página Designer de formato.](./media/er-design-configuration-word-image3.gif)

Você pode adicionar os elementos aninhados **Excel\\Range** e **Excel\\Cell** para o elemento **Excel\\File** para especificar a estrutura dos dados que serão inseridos nos relatórios gerados no tempo de execução. Em seguida, você deve vincular esses elementos a fontes de dados do formato de ER editável para especificar os dados reais que serão inseridos nos relatórios gerados no tempo de execução.

![Adicionar elemento aninhados na página Designer de formato.](./media/er-design-configuration-word-image4.gif)

Quando você salva as alterações no formato de ER no momento da criação, a estrutura de formato hierárquico é armazenada no modelo do Word anexado como uma [parte XML personalizada](/visualstudio/vsto/custom-xml-parts-overview) que é denominada **Relatório**. Você deve acessar o modelo modificado, baixá-lo no Finance, armazená-lo localmente e abri-lo no aplicativo da área de trabalho Word. A ilustração a seguir mostra o modelo de exemplo armazenado localmente para o relatório de controle que contém a parte XML personalizada **Relatório**.

![Pré-visualizar o modelo de exemplo de relatório no aplicativo da área de trabalho Word.](./media/er-design-configuration-word-image5.gif)

Quando as associações dos elementos de formato **Excel\\Range** e **Excel\\Cell** são executadas no tempo de execução, todas as associações fornecem dados no documento gerado do Word como um campo individual da parte XML personalizada do **Relatório**. Para inserir os valores dos campos da parte XML personalizada em um documento gerado, você deve adicionar os [controles de conteúdo](/office/client-developer/word/content-controls-in-word) adequados do Word ao modelo do Word para servir como espaços reservados para dados que serão preenchidos no tempo de execução. Para especificar como os controles de conteúdo são preenchidos, mapeie cada controle de conteúdo para o campo apropriado da parte XML personalizada **Relatório**.

![Adicionar e mapear controles de conteúdo no aplicativo da área de trabalho Word.](./media/er-design-configuration-word-image6.gif)

Em seguida, você deve substituir o modelo original do Word do formato de ER editável pelo modelo modificado que agora contém os controles de conteúdo do Word que foram mapeados para os campos da parte XML personalizada **Relatório**.

![Substituir o modelo na página Designer de formato.](./media/er-design-configuration-word-image7.gif)

Quando você executa o formato de ER configurado, o modelo anexado do Word é usado para gerar um novo relatório. Os dados reais são armazenados no relatório do Word como uma parte XML personalizada que é denominada **Relatório**. Quando o relatório gerado é aberto, os controles de conteúdo do Word são preenchidos com dados da parte XML personalizada **Relatório**.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**Pergunta:** configurei um formato de ER para imprimir um documento do Word que contém um endereço da empresa. No modelo do Word para esse formato de ER, inseri um controle de conteúdo de rich text para apresentar um endereço da empresa. No Finance, inseri o endereço da empresa como texto de várias linhas e selecionei **Enter** para adicionar um retorno de carro a cada linha inserida. Portanto, quero que o endereço da empresa apareça como texto de várias linhas nos documentos gerados. No entanto, o endereço aparece como uma única linha de texto que contém símbolos especiais, em vez de retornos de carro. O que há de errado nas minhas configurações?

**Resposta:** em vez de usar um controle de conteúdo de rich text, você deve usar um controle de conteúdo de texto simples e marcar a caixa de seleção **Permitir retornos de carro (vários parágrafos)** nas propriedades do controle.

## <a name="additional-resources"></a>Recursos adicionais

- [Reutilizar configurações de ER com modelos do Excel para gerar relatórios no formatos Word](./tasks/er-design-configuration-word-2016-11.md)
- [Inserir imagens e formas em documentos que você gerar usando ER](electronic-reporting-embed-images-shapes.md#embed-an-image-in-a-word-document)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
