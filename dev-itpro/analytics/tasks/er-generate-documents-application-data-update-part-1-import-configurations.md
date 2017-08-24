--- 
title: "Importar configurações para gerar documentos com atualização de dados de aplicativo para relatório eletrônico (ER)"
description: "Para completar as etapas, neste procedimento você deve primeiro concluir o procedimento, \"ER Criar um provedor de configuração e marcá-lo como ativo\"."
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 7085e92b85a5003334c19598de632fcaf08da49e
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="import-configurations-to-generate-documents-with-application-data-update-for-electronic-reporting-er"></a>Importar configurações para gerar documentos com atualização de dados de aplicativo para relatório eletrônico (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Para completar as etapas, neste procedimento você deve primeiro concluir o procedimento, "ER Criar um provedor de configuração e marcá-lo como ativo".

As etapas desse procedimento explicam como criar configurações de Relatório eletrônico (ER) para gerar um documento eletrônico. Nesse procedimento, você importará as configurações de ER necessárias que foram criadas para a empresa exemplo, Litware, Inc., e usá-las para gerar documentos eletrônicos. Este procedimento é criado para usuários com a função atribuída de administrador do sistema ou desenvolvedor de relatório eletrônico. Estas etapas podem ser concluídas usando o conjunto de dados de DEMF. Antes de começar, baixe e salve os arquivos listados no tópico da Ajuda, "Gerar documentos eletrônicos e atualizar dados do aplicativo com a ferramenta de Relatórios eletrônico" (https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/analytics/generate-electronic-documents-update-application-data/). Os arquivos são Intrastat (model).xml, Intrastat (mapping).xml e Intrastat (format).xml.

1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.
    * Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como Ativo. Se não visualizar este provedor de configuração, conclua as etapas no procedimento Criar um provedor de configuração e marcá-lo como ativo.  
    * As etapas deste procedimento mostram como usar recursos de ER para concluir uma atualização de dados do aplicativo e como gerar um relatório Intrastat. Os detalhes do processo de relatório são arquivados em tabelas do aplicativo. Atualmente, quando o processo de relatório Intrastat é ativado no formulário Intrastat, o arquivamento é feito com base na lógica programada do código-fonte existente. Nesse procedimento, você configurará uma lógica semelhante simplificada de dados de aplicativo usando somente a estrutura de ER. Nenhuma alteração será feita ao código-fonte.   

## <a name="import-er-configurations"></a>Importar configurações de ER
1. Clique em Configurações de relatórios.
2. Clique em Trocar.
3. Clique em Carregar de um arquivo XML.
    * Importe a configuração do modelo de ER que contém o modelo de dados criado para ser usado como a fonte de dados para gerar o relatório Intrastat. Posteriormente, você estenderá esta definição do modelo de dados para usá-las para uma atualização de dados do aplicativo para arquivar detalhes do processo do relatório Intrastat.   
    * Clique em Procurar e selecione o arquivo Intrastat (model).xml.  
4. Clique em OK.
5. Na árvore, selecione 'Intrastat (model)'.
6. Clique em Designer.
7. Na árvore, expanda 'Para documento de saída'.
8. Na árvore, expanda 'Para documento de saída\Transações'.
    * Revise a estrutura do modelo de dados importado. Observe que o item raiz "Para documento de saída" é definido para especificar o fluxo de dados para obter dados do aplicativo e usá-lo como origem de dados para gerar o relatório Intrastat. As "Transações (lista de registros)" são usadas para representar a lista de transações Intrastat que devem ser reportadas. Como você arquivará códigos de mercadoria reportados, o identificador exclusive de um código de mercadoria único "Id rec mercadoria (Int64)" é necessário neste fluxo de dados.   
9. Feche a página.
10. Clique em Trocar.
11. Clique em Carregar de um arquivo XML.
    * Importe a configuração de mapeamento de ER que especifica o fluxo de dados para obter dados do aplicativo e usá-los para gerar o relatório Intrastat. Posteriormente, você estenderá esta definição de mapeamento de modelo para obter dados do relatório Intrastat e usá-lo para atualização de dados do aplicativo para arquivar detalhes do processo do relatório Intrastat.   
    * Clique em Procurar e selecione o arquivo Intrastat (mapping).xml.  
12. Clique em OK.
13. Na árvore, expanda 'Intrastat (model)'.
14. Na árvore, selecione 'Intrastat (modelo)\Intrastat (mapeamento)'.
15. Clique em Designer.
    * Observe que o mapeamento de modelo atual contém o valor "Para modelo" no campo Direção. Isso significa que esse mapeamento modelo foi criado obtendo dados de aplicativo e armazenando-os no modelo de dados.  
16. Clique em Designer.
17. Na árvore, expanda 'Lista'.
18. Na árvore, expanda 'Transações= Lista'.
    * Reveja a estrutura de mapeamento do modelo que usa o modelo de dados que é filtrado com base no item raiz 'Para documento de saída'. Observe que a fonte de dados adicionada, ‘Lista’, fornece acesso a dados de aplicativo necessários, que é a lista de registros de tabela intrastat.  
19. Feche a página.
20. Feche a página.
21. Clique em Trocar.
22. Clique em Carregar de um arquivo XML.
    * Importe a configuração de formato de ER que especifica o layout do relatório Intrastat e o processo de preenchimento de dados para o relatório. Posteriormente, você estenderá esta definição de formato para colocar dados do relatório Intrastat no modelo de dados e depois usá-lo para atualização de dados do aplicativo para arquivar os detalhes do processo do relatório Intrastat.   
    * Clique em Procurar e selecione o arquivo Intrastat (format).xml.  
23. Clique em OK.
24. Na árvore, selecione 'Intrastat (modelo)\Intrastat (formato)'.
25. Clique em Designer.
26. Clique em Expandir/recolher.
27. Na árvore, selecione 'Arquivo\Declaração'.
28. Clique na aba Mapeamento.
29. Na árvore, selecione 'Arquivo'.
    * Examine a estrutura do formato usado para gerar o relatório intrastat. Observe que ele foi criado para gerar um arquivo XML preenchendo dados do modelo de dados, que está baseado no item raiz 'Para documento de saída'. Verifique se o nome do arquivo gerado está definido no formulário da caixa de diálogo (a fonte de dados 'fn' é usada para isso.)   
30. Feche a página.


