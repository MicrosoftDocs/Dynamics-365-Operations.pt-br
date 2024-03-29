---
title: Criar um modelo de configuração do produto
description: Este procedimento mostra como criar um modelo de configuração do produto e especificar as informações básicas, como atributos e subcomponentes.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCCreateProductConfigurationModel, PCProductConfigurationModelDetails, PCBOMLineDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ca99c0346a3f982164076167c3429587aac18be6
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7568415"
---
# <a name="create-a-product-configuration-model"></a>Criar um modelo de configuração do produto

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como criar um modelo de configuração do produto e especificar as informações básicas, como atributos e subcomponentes. A empresa de dados demo usada para criar este procedimento é USMF.


## <a name="create-a-product-model"></a>Criar um modelo de produto

1. Acesse **Gerenciamento de informações do produto \> Produtos \> Modelos de configuração do produto**.
1. Selecione **Novo**.
1. No campo **Nome**, digite um valor.
1. No campo **Descrição**, digite um valor.
1. No campo **Estratégia do agente de resolução**, selecione uma opção.
    * A estratégia do agente de resolução determina como as restrições no modelo de configuração de produto baseada em restrições são processadas. A seleção pode ter impacto sobre o desempenho do modelo de configuração de produto.  
1. No campo **Nome**, digite um valor.
    * O componente raiz representa o modelo de configuração de produto, mas ele pode ser usado em outros modelos de produto.  
1. Selecione **OK**.
1. No campo **Reutilizar configurações**, selecione uma opção.
    * Se o parâmetro de reutilização de configurações for definido como Sim, o sistema verificará se há configurações idênticas após a sessão de configuração e fará o reuso quando uma combinação exata for encontrada.  

## <a name="add-attributes"></a>Adicionar atributos

1. Expanda a seção **Atributos**.
2. Selecione **Adicionar**.
3. Na lista, marque a linha selecionada.
4. No campo **Nome**, digite um valor.
5. No campo **Nome do agente de resolução**, digite um valor.
    * O nome do agente de resolução é usado pelo agente de resolução de restrição do configurador de produtos. Ele não deve incluir espaços ou caracteres especiais, exceto _ (sublinhado).  
6. No campo **Descrição**, digite um valor.
    * O texto de descrição é exibido ao usuário da configuração e, portanto, pode ajudar na seleção do valor de atributo correto.  
7. No campo **Tipo de atributo** insira ou selecione um valor.
    * O tipo de atributo determina quais valores estão disponíveis para o atributo.  
8. Marque a caixa de seleção **Incluir em reutilização**.
    * Essa opção só está disponível quando a opção Reutilizar configurações for selecionada. A inclusão do atributo na caixa de seleção de reutilização significa que esse atributo será considerado quando o sistema estiver à procura de uma combinação exata.  

## <a name="add-subcomponents"></a>Adicionar subcomponentes

1. Expanda a seção **Subcomponentes**.
2. Selecione **Adicionar**.
3. Na lista, marque a linha selecionada.
4. No campo **Nome**, digite um valor.
5. No campo **Nome do agente de resolução**, digite um valor.
6. No campo **Descrição**, digite um valor.
7. No campo **Componente** insira ou selecione um valor.
    * Cada subcomponente deve fazer referência a uma definição de componente. Esse design oferece suporte a componentes reutilizáveis e garante que, após ser definido, o componente possa ser usado em muitos modelos de produto.  
8. Selecione **Salvar**.
9. Selecione **Detalhes da linha de BOM**.
    * O formulário Detalhes da linha de BOM permite que o usuário selecione as propriedades necessárias para o subcomponente. Cada propriedade pode receber um valor fixo ou mapeada para um atributo. O mapeamento para um atributo resultará na propriedade de linha de BOM obtendo diferentes valores conforme a seleção de configuração.  
10. No campo **Número do item**, insira ou selecione um valor.
    * Cada subcomponente representa um produto mestre configurável com a tecnologia de configuração baseada em restrições. A referência é feita por meio do número do item.  
11. Marque a caixa de seleção **Definir**.
12. Selecione **Sim** no campo **Cálculo**.
    * Definir a opção de cálculo garante que o produto será incluído ao executar um cálculo de custo para o produto.  
13. Selecione a guia **Configuração**.
14. Marque a caixa de seleção **Definir**.
15. No campo **Quantidade.**, insira um número
    * O campo quantidade determina o quanto desse produto será consumido no produto configurado.  
16. Marque a caixa de seleção **Definir**.
17. No campo **Por série**, informe um número.
18. Selecione **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]