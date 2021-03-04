---
title: Use um caminho relativo em associações de dados de modelos e formatos de ER
description: A ferramenta ER (relatório eletrônico) permite que usuários definam estruturas em formato eletrônico e descrevam como essas estruturas devem ser preenchidas com dados e algoritmos existentes no aplicativo.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERModelMappingDesigner, EROperationDesigner, ERExpressionDesignerFormula
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 5e2554dc33514185fa16868ee239c3e44ff675dd
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687447"
---
# <a name="use-a-relative-path-in-data-bindings-of-er-models-and-formats"></a>Use um caminho relativo em associações de dados de modelos e formatos de ER

[!include[banner](../includes/banner.md)]

A ferramenta ER (relatório eletrônico) permite que usuários definam estruturas em formato eletrônico e descrevam como essas estruturas devem ser preenchidas com dados e algoritmos existentes no aplicativo. Para obter mais informações, consulte [Criar configurações do ER (relatório eletrônico)](electronic-reporting-configuration.md). Para especificar o fluxo de dados para recuperar dados do Finance and Operations e usá-los para gerar um documento eletrônico, você precisa fazer o seguinte:

- Associar fontes de dados configurados para elementos do [modelo de dados](general-electronic-reporting.md#data-model-and-model-mapping-components) específico do domínio criado. A estrutura de modelo e as fontes de dados selecionadas podem ser parte de uma estrutura hierárquica complexa. Por causa disso, as associações finais podem ser grandes o suficiente e conter muitos elementos de tipos diferentes (por exemplo, relações, tabelas e métodos). As associações podem ficar menos legíveis e mais complexas para examinar e entender, especialmente para não proprietários. 
- Associe elementos do modelo de dados com componentes de [formato](general-electronic-reporting.md#FormatComponentOutbound) para definir quais dados serão preenchidos do modelo de dados para a saída do formato gerado.

Para melhorar a usabilidade de designers de mapeamento do ER, o recurso de [caminho relativo](er-formula-language.md#relative-path) foi liberado. Por padrão, a opção da representação de caminho relativo será ativada para qualquer nova instância do aplicativo em que a experiência de design do ER estiver habilitada (Microsoft Dynamics 365 Finance, Microsoft Regulatory Configuration Service). Implementamos o parâmetro de caminho relativo para que os usuários possam continuar usando o caminho completo ao trabalhar com esta apresentação de associações do ER.

[![Parâmetros de usuário](./media/relative-path-01.png)](./media/relative-path-01.png)

 
Quando o parâmetro de uso do caminho relativo está ativado, um único caractere @ substitui o caminho para o item pai na associação do elemento de modelo atual. O caminho de associação inteiro fica mais curto, o que torna o mapeamento inteiro mais óbvio e de compreensão mais fácil. Na maioria dos casos, não são necessários rolamentos adicionais no designer do ER para exibir todas as associações do modelo de dados.

[![Designer de mapeamento de modelo](./media/relative-path-02.png)](./media/relative-path-02.png)
 
Ao começar a criar uma nova expressão de ER, você precisa inserir somente um caractere para definir uma associação para um campo do item pai.

[![Designer de fórmulas](./media/relative-path-03.png)](./media/relative-path-03.png)
 
Quando decidir alterar a fonte de dados do item de modelo pai, com uso do caminho absoluto, você precisará reassociar manualmente este item de modelo, bem como todos os itens aninhados, para uma nova fonte de dados. Quando o uso do caminho relativo estiver ativado e você selecionar uma nova fonte de dados a ser associada a um item pai, terá a opção de reassociar automaticamente todos os elementos aninhados desse item pai com um clique.

[![Substituir a mensagem de caminho existente](./media/relative-path-04.png)](./media/relative-path-04.png)
 
Se você confirmar a reassociação de itens aninhados, o novo item pai será colocado no caminho de cada item aninhado contendo o item pai existente.
Este recurso não elimina a compatibilidade com versões anteriores da estrutura do ER. Todas as configurações do ER criadas previamente trabalharão com esse novo recurso. Não são necessárias atualizações ou conversões.

> [!NOTE]
> Todas as alterações que foram apresentadas pela modificação em massa de associações de elementos aninhados em mapeamentos de modelo são salvas corretamente em um delta de configuração (rastreamento de alterações). Isso permite que os clientes troquem a base da versão derivada de mapeamentos de modelo para qualquer nova versão de base dele que tenha sido modificada usando este recurso novo.

## <a name="additional-resources"></a>Recursos adicionais

[Linguagem da fórmula do ER](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]