---
title: Acesse metadados de aplicativos usando a configuração de ER
description: O tópico descreve como um usuário do Regulatory Configuration Service (RCS) pode criar um novo mapeamento de modelo de relatório eletrônico (ER) usando os metadados.
author: NickSelin
manager: AnnBe
ms.date: 06/28/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 58697148ecf83f4962bd64a221945b6d911e11a6
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093296"
---
# <a name="access-application-metadata-by-using-er-configuration"></a>Acesse metadados de aplicativos usando a configuração de ER

[!include [banner](../../includes/banner.md)]

As etapas a seguir explicam como um usuário do Regulatory Configuration Service (RCS) na função de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar um novo mapeamento de modelos de relatório eletrônico (ER) por meio dos metadados do aplicativo. Os metadados do aplicativo serão acessados por meio de uma configuração de metadados de ER contendo um conjunto de exemplo de metadados para acessar transações de comércio exterior. Para concluir estas etapas no RCS, primeiro é necessário concluir as etapas no procedimento do tópico, [Criar provedores de configuração e marcá-los como ativos](er-configuration-provider-mark-it-active-2016-11.md). Em seguida, conclua as etapas no tópico [Preparar metadados do aplicativo a serem usados no RCS](prepare-application-metadata-rcs.md).

## <a name="prerequisites"></a>Pré-requisitos
1. Vá para **Todos os espaços de trabalho** > **Relatório eletrônico**. 
2. Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como **Ativo**. Se você não visualizar este provedor de configuração, conclua as etapas no procedimento [Criar provedores de configuração e marcá-los como ativos](er-configuration-provider-mark-it-active-2016-11.md). 

## <a name="import-metadata-configuration"></a>Importar configuração de metadados 
1. Clique em **Configurações de metadados**. 
2. Importe a configuração de metadados de ER que contém metadados que foram configurados para gerar documentos eletrônicos para negócios de comércio exterior. Essa configuração de metadados de ER foi exportada como arquivo XML enquanto as etapas no procedimento [Preparar metadados do aplicativo a serem usados no RCS](prepare-application-metadata-rcs.md) foram concluídas. 
3. Clique em **Taxa de câmbio**. 
4. Clique em **Carregar de um arquivo XML**. 
5. Clique em **Procurar** e selecione o arquivo "Foreign trade metadata.xml". 
6. Clique em **OK**. 
7. Feche a página. 

## <a name="create-data-model-configuration"></a>Crie a configuração de modelo de dados
1. Clique em **Configurações de relatórios**. 
2. Clique em **Criar configuração** para abrir a caixa de diálogo suspensa. 
3. No campo **Nome**, digite 'Modelo de comércio exterior'. 
4. Clique em **Criar configuração**. 
5. Clique em **Designer**. 
6. Clique em **Novo** para abrir a caixa de diálogo suspensa. 
7. No campo **Nome**, digite 'Raiz'. 
8. Clique em **Adicionar**. 
9. Clique em **Novo** para abrir a caixa de diálogo suspensa. 
10.    No campo **Nome**, digite 'Transação'. 
11.    No campo **Tipo de item**, selecione **Lista de registros**. 
12.    Clique em **Adicionar**. 
13.    Clique em **Novo** para abrir a caixa de diálogo suspensa. 
14.    No campo **Nome**, digite 'Código de mercadoria'. 
15.    No campo **Tipo de item**, selecione **String**. 
16.    Clique em **Adicionar**. 
17.    Clique em **Novo** para abrir a caixa de diálogo suspensa. 
18.    No campo **Nome**, digite 'Valor faturado'. 
19.    No campo **Tipo de item**, selecione **Real**. 
20.    Clique em **Adicionar**. 
21.    Clique em **Novo** para abrir a caixa de diálogo suspensa. 
22.    No campo **Nome**, digite 'Data'. 
23.    No campo **Tipo de item**, selecione **Data**. 
24.    Clique em **Adicionar**. 
25.    Clique em **Referência raiz**. 
26.    Clique em **OK**. 
27.    Clique em **Salvar**. 
28.    Feche a página. 
29.    Clique em **Alterar status**. 
30.    Clique em **Concluir**. 
31.    Clique em **OK**. 

## <a name="create-model-mapping-configuration"></a>Crie uma configuração de mapeamento de modelo 
1. Clique em **Criar configuração** para abrir a caixa de diálogo suspensa. 
2. No campo **Novo**, insira 'Mapeamento de modelo baseado no modelo de comércio exterior de modelo de dados'. 
3. No campo **Nome**, digite 'Mapeamento de comércio exterior'. 
4. Clique em **Criar configuração**. 
5. Expanda a seção **Pré-requisitos**. 
6. Clique em **Editar**. 
7. Clique em **Novo**. 
8. Na lista, marque a linha selecionada. 
9. No campo **Tipo de componente de pré-requisito**, selecione **Configuração**. 
10.    Selecione a configuração de **Metadados de comércio exterior**. 
11.    Clique em **Salvar**. 
12.    Adicionamos a referência à versão 1 da configuração de "Metadados de comércio exterior". Os metadados de aplicativos dessa configuração serão oferecidos durante a criação desse mapeamento de modelo. 
13.    Feche a página. 
14.    Clique em **Designer**. 
15.    Clique em **Designer**. 
16.    Na árvore, selecione **Dynamics 365 for Operations\Registros da tabela**. 
17.    Clique em **Adicionar raiz**. 
18.    No campo **Nome**, digite 'Intrastat'. 
19.    Selecione registros de tabela **Intrastat**. 
20.    Clique em **OK**. 

> [!NOTE]
> As 2 únicas tabelas foram oferecidas porque as 2 únicas tabelas foram adicionadas no conjunto de metadados em uso no momento. 

21.    Clique em **Associar**. 
22.    Na árvore, expanda **Intrastat**. 
23.    Na árvore, selecione **Intrastat\AmountMST**. 
24.    Na árvore, expanda **Transação = Intrastat**. 
25.    Na árvore, selecione **Transação = Intrastat\Valor faturado**. 
26.    Clique em **Associar**. 
27.    Na árvore, selecione **Intrastat\TransDate**. 
28.    Na árvore, selecione **Transação = Intrastat\Data**. 
29.    Clique em **Associar**. 
30.    Na árvore, expanda **Intrastat\>Relações**. 
31.    Na árvore, expanda **Intrastat\>Relações\IntrastatCommodity**. 
32.    Na árvore, selecione **Intrastat\>Relações\IntrastatCommodity\Código**. 
33.    Na árvore, selecione **Transação = Intrastat\Código de mercadoria**. 
34.    Clique em **Associar**. 
35.    Clique em **Validar**. 

> [!NOTE]
> Associamos com êxito elementos de modelo de dados com itens de fontes de dados que serão descritos usando detalhes de metadados de aplicativo da configuração de metadados de ER referenciada. 
36.    Clique em **Salvar**. 
37.    Feche a página. 
38.    Feche a página. 
39.    Se necessário, você pode estender o conjunto de metadados existente e exportar a nova versão concluída da configuração de metadados de ER. Em seguida, é possível importá-la para o RCS e atualizar os pré-requisitos da configuração de mapeamento de modelos configurado que se refere a uma nova versão da configuração de metadados importada. 

> [!NOTE]
> Essa forma de obter informações sobre os metadados de aplicativos é a única disponível para aplicativos implantados localmente (quando dados corporativos locais (LBD) ou o modelo de implantação local são usados).
        


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]