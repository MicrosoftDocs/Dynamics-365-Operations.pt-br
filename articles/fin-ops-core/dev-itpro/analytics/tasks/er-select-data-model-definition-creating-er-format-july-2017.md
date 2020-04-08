---
title: Selecionar definições de modelo de dados ao criar formatos
description: Para completar as etapas, neste procedimento você deve primeiro concluir o procedimento, ER Criar um provedor de configuração e marcá-lo como ativo.
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 374c31b5ea9160fba773e82f658e8de05c67cab4
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143237"
---
# <a name="select-data-model-definitions-when-you-create-formats"></a>Selecionar definições de modelo de dados ao criar formatos

[!include [banner](../../includes/banner.md)]

Para completar as etapas, neste procedimento você deve primeiro concluir o procedimento, ER Criar um provedor de configuração e marcá-lo como ativo. 

Este procedimento mostra como o item raiz de modelo pode ser selecionado como uma definição do modelo de dados para inserir uma configuração de formato de relatório eletrônico (ER) que é designada para gerar documentos eletrônicos. Neste procedimento, você irá adicionar uma nova configuração de formato de ER para a empresa exemplo, Litware, Inc. 

Esse procedimento é destinado a usuários com a função de Administrador do sistema ou Desenvolvedor de relatório eletrônico. As etapas podem ser concluídas usando qualquer conjunto de dados.

1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.
    * Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como Ativo. Se não visualizar este provedor de configuração, conclua as etapas no procedimento Criar um provedor de configuração e marcá-lo como ativo.  
2. Clique em Configurações de relatórios.

## <a name="add-a-new-er-data-model-configuration"></a>Adicionar uma nova configuração de modelo de dados do ER
1. Clique em Criar configuração para abrir a caixa de diálogo suspensa.
    * Adicionamos uma nova configuração do modelo de ER que contém o modelo de dados criado para ser usado como a fonte de dados para geração de relatórios de ER.  
2. No campo Nome, digite 'Modelo de pagamento (fictício)'.
    * Modelo de pagamento (fictício)  
3. Clique em Criar configuração.
4. Clique em Designer.
    * Abra o designer de ER para especificar a estrutura do modelo de dados dessa configuração.  
    * Suponha que criamos o modelo de dados para o domínio comercial de pagamentos para suportar 2 métodos de pagamento – transferência de crédito e débito direto.  
5. Clique em Novo para abrir a caixa de diálogo suspensa.
6. No campo Nome, digite 'Pagamentos - transferência de crédito'.
    * Pagamentos - transferência de crédito  
7. Clique em Adicionar.
8. Clique em Novo para abrir a caixa de diálogo suspensa.
9. No campo Novo nó como um, insira "Raiz do modelo".
10. No campo Nome, digite 'Pagamentos - débito direto'.
    * Pagamentos - débito direto  
11. Clique em Adicionar.
12. Clique em Salvar.
13. Feche a página.
14. Clique em Alterar status.
    * Preencha a versão de rascunho do modelo para disponibilizá-lo nos novos mapeamentos e formatos do modelo.  
15. Clique em Concluir.
16. Clique em OK.

## <a name="start-to-enter-a-new-er-format-configuration"></a>Começar a inserir uma nova configuração de formato de ER
1. Clique em Criar configuração para abrir a caixa de diálogo suspensa.
2. No campo Novo, insira 'Formato baseado no modelo de dados Modelo de pagamento (fictício)'.
3. No campo Definição do modelo de dados, insira ou selecione um valor.
    * Observe que todos os itens raiz do modelo de dados selecionado estão disponíveis atualmente para seleção como uma definição do modelo de dados. Você pode continuar a criar seu formato usando alguns itens raiz necessários do modelo de dados. Um mapeamento de modelo ausente para o item raiz selecionado não impede que você prossiga.  
4. Feche a página.

## <a name="add-a-new-er-model-mapping-configuration"></a>Adicionar uma nova configuração de mapeamento do modelo de ER
1. Clique em Criar configuração para abrir a caixa de diálogo suspensa.
2. No campo Novo, insira 'Mapeamento de modelo baseado no modelo de dados Modelo de pagamento (fictício)'.
3. No campo Nome, digite 'Mapeamento de modelo de pagamento (fictício)'.
    * Mapeamentos de modelo de pagamento (fictício)  
4. No campo Definição do modelo de dados, insira ou selecione um valor.
5. Clique em Criar configuração.

## <a name="design-er-model-mappings"></a>Criar mapeamentos de modelo de ER
1. Clique em Designer.
    * Use o designer de ER para especificar os mapeamentos de modelo para os itens raiz necessários.  
2. Clique em Designer.
    * Simule a definição de mapeamento de modelo selecionado para o item da raiz do modelo selecionado.  
3. Na árvore, selecione 'Dynamics 365 for Operations\Registros da tabela'.
4. Clique em Adicionar raiz.
5. No campo Nome, digite 'Razão'.
6. No campo Tabela, digite 'LedgerJournalTrans'.
    * LedgerJournalTrans  
7. Clique em OK.
8. Clique em Salvar.
9. Feche a página.
10. Feche a página.

## <a name="start-to-enter-another-new-er-format-configuration"></a>Começar a inserir outra nova configuração de formato de ER
1. Na árvore, selecione 'Modelo de pagamento (fictício)'.
2. Clique em Criar configuração para abrir a caixa de diálogo suspensa.
3. No campo Novo, insira 'Formato baseado no modelo de dados Modelo de pagamento (fictício)'.
4. No campo Definição do modelo de dados, insira ou selecione um valor.
    * Observe que agora um só item raiz está disponível para mapear fontes de dados do aplicativo. Quando pelo menos um mapeamento de modelo foi introduzido, somente os itens raiz de modelo que são mapeados para fontes de dados do aplicativo poderão ser selecionados como uma definição modelo, quando o formato de ER for adicionado.   
5. Feche a página.

