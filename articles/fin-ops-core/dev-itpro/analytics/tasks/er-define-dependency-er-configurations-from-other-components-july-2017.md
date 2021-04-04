---
title: Definir a dependência de configurações ER em outros componentes
description: Este tópico descreve como criar uma configuração de relatório eletrônico e especificar sua dependência de outros componentes de software.
author: NickSelin
manager: AnnBe
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d37a10b1430349014f55cde155c6ed6e85dfe3dc
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567309"
---
# <a name="define-the-dependency-of-er-configurations-on-other-components"></a>Definir a dependência de configurações ER em outros componentes

[!include [banner](../../includes/banner.md)]

Para executar estas etapas, primeiro você deve executar as etapas no guia de tarefas, ER Gerenciar configurações do mapeamento de modelo, e deve ter acesso ao Microsoft Dynamics Lifecycle Services (LCS).

Este procedimento mostra como criar uma configuração de relatório eletrônico (ER) e especificar sua dependência de outros componentes de software, para ajudar a garantir que a configuração seja baixada corretamente para uma versão específica do Finance and Operations. Neste exemplo, você criará as configurações de ER necessárias para a empresa exemplo, Litware, Inc. 

Esse procedimento é destinado a usuários com a função de Administrador do sistema ou Desenvolvedor de relatório eletrônico. As etapas podem ser realizadas em qualquer empresa, porque as configurações de ER são compartilhadas entre as empresas. 

1. Vá para Administração da organização > Relatório eletrônico > Configurações.
    * Verifique se a árvore de configurações contém a configuração de "Modelo de dados de amostra" e subordine os itens. Se não, conclua as etapas na guia de tarefas, ER Gerenciar configurações de mapeamento de modelo, e inicie este guia novamente.   

## <a name="define-the-dependency-of-er-configurations-from-other-components"></a>Definir a dependência de configurações de ER de outros componentes
1. Na árvore, expanda 'Modelo de dados de amostra'.
2. Na árvore, selecione "Modelo de dados de amostra\Mapeamento de amostra".
    * Nós selecionamos a versão de rascunho da configuração de mapeamento do modelo "Mapeamento de amostra". Nós definiremos agora sua dependência de outros componentes de software. Esta etapa é considerada um pré-requisito para controlar o download de versão de configuração de um repositório de ER e qualquer outro uso desta versão.   
3. Expanda a seção Pré-requisitos.
    * Observe que o grupo de pré-requisitos "Implementações" foi adicionado automaticamente a este estágio. Este grupo contém o componente de pré-requisito que se refere à configuração do modelo de dados e têm o sinalizador de implementação ativado. Este sinalizador indica que a configuração de mapeamento "Mapeamento de amostra" é considerada a implementação do modelo de dados "Modelo de dados de amostra". Este componente forçará o ER para baixar a configuração de mapeamento "Mapeamento de amostra" de um repositório de ER sempre que a configuração do modelo "Modelo de dados de amostra" for baixada.   
4. Clique em Editar.
    * Uma dependência única da versão atual de uma configuração de um componente de software pode ser especificada usando a definição do tipo de componente, e a versão do componente ou um intervalo de versões do componente.  
    * As dependências desejadas podem ser agrupadas. Quando o tipo de agrupamento "Todos de" for selecionado, a condição de dependência desse grupo será considerada preenchida quando cada condição de dependência deste grupo e do grupo subordinado é preenchida. Quando o tipo de agrupamento "Um de" for selecionado, a condição de dependência desse grupo será considerada preenchida quando pelo menos uma condição de dependência deste grupo for preenchida.   
5. Clique em Novo.
6. Selecione o componente de pré-requisito do Produto.
7. Selecione Microsoft Dynamics 365 for Operations (1611).
8. No campo Versão, digite '[7.1.1541.3036,8)'.
    * [7.1.1541.3036,8)  
    * As dependências que você inserir serão avaliadas quando esta configuração for baixada de qualquer repositório de ER. Esta versão da configuração será baixada do repositório de ER quando a versão 1 da configuração do "Modelo de dados de amostra" já estiver em vigor ou baixada previamente. Se tiver sido baixada com antecedência, ela deverá ser concluída no Finance and Operations versão 7.1.1541.3036 ou posterior, mas não pode exceder a versão principal 8.   
9. Clique em Salvar.
10. Feche a página.
11. Clique em Alterar status.
12. Clique em Concluir.
13. Clique em OK.
14. Na árvore, selecione "Modelo de dados de amostra\Mapeamento de amostra (alternativo)".
15. Clique em Editar.
16. Clique em Novo.
17. Selecione o componente de pré-requisito do Produto.
18. Selecione Microsoft Dynamics AX 7.0 RTW.
19. No campo Versão, digite '[7.0.1265.3015,7.1)'.
    * [7.0.1265.3015,7.1)  
    * As dependências serão avaliadas quando a configuração for baixada de um repositório de ER. Esta versão da configuração será baixada do repositório de ER quando a versão 1 da configuração do "Modelo de dados de amostra" já estiver em vigor ou baixada previamente. Se tiver sido baixada com antecedência, deverá ser executada no Microsoft Dynamics 365 for Finance and Operations Enterprise Edition, cuja versão deve ser 7.0.1265.3015 ou posterior, mas não pode exceder a versão secundária 1.   
20. Clique em Salvar.
21. Feche a página.
22. Clique em Alterar status.
23. Clique em Concluir.
24. Clique em OK.

## <a name="configure-the-er-repository"></a>Configurar o repositório de ER
1. Feche a página.
2. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.
    * Abra a lista de repositórios do ER do fornecedor de ER atual, Litware, Inc.  
3. Na lista, marque a linha selecionada.
4. Clique em Repositórios.
5. Clique em Mostrar filtros.
6. Insira um valor de filtro "LCS" no campo "Nome do tipo" usando o operador de filtro "contém".
    * Se o repositório de LCS já estiver registrado para o provedor de ER atual, você poderá ignorar as etapas restantes desta subtarefa. Se o repositório de LCS ainda não estiver registrado, conclua as etapas restantes.   
7. Clique em Adicionar para abrir a caixa de diálogo suspensa.
8. No campo Tipo de repositório de configuração, insira 'LCS'.
9. Clique em Criar repositório.
10. No campo Projeto, insira ou selecione um valor.
    * Selecione o projeto LCS desejado da pesquisa do campo "Projeto".  
11. Clique em OK.
12. Feche a página.

## <a name="upload-configurations-to-lcs"></a>Carregar a configuração para o LCS
1. Clique em Configurações de relatórios.
2. Na árvore, selecione 'Modelo de dados de amostra'.
3. Selecione a versão concluída desta configuração.
4. Clique em Alterar status.
5. Clique em Compartilhar.
6. Clique em OK.
    * A versão 1 dessa configuração modelo foi carregada para LCS usando o projeto de LCS para o repositório de ER configurado anteriormente.   
7. Na árvore, expanda 'Modelo de dados de amostra'.
8. Na árvore, selecione "Modelo de dados de amostra\Mapeamento de amostra".
9. Selecione a versão concluída desta configuração.
10. Clique em Alterar status.
11. Clique em Compartilhar.
12. Clique em OK.
    * A versão 1.1 dessa configuração de mapeamento de modelo foi carregada para LCS usando o projeto de LCS para o repositório de ER configurado anteriormente.   
13. Na árvore, selecione "Modelo de dados de amostra\Mapeamento de amostra (alternativo)".
14. Selecione a versão concluída desta configuração.
15. Clique em Alterar status.
16. Clique em Compartilhar.
17. Clique em OK.
    * A versão 1.1 dessa configuração de mapeamento de modelo foi carregada para LCS usando o projeto de LCS para o repositório de ER configurado anteriormente.   

## <a name="evaluate-er-configuration-dependencies"></a>Avaliar dependências de configuração de ER
Excluiremos as configurações criadas do sistema e as baixaremos novamente do repositório LCS.  
1. Na árvore, selecione "Modelo de dados de amostra\Mapeamento de amostra".
2. Clique em Excluir.
3. Clique em Sim.
4. Na árvore, selecione "Modelo de dados de amostra\Mapeamento de amostra (alternativo)".
5. Clique em Excluir.
6. Clique em Sim.
7. Na árvore, selecione "Modelo de dados de amostra\Formato de amostra".
8. Clique em Excluir.
9. Clique em Sim.
10. Na árvore, selecione 'Modelo de dados de amostra'.
11. Clique em Excluir.
12. Clique em Sim.
13. Feche a página.
    * Abra a lista de repositórios do ER do fornecedor de ER atual, Litware, Inc.  
14. Clique em Repositórios.
15. Clique em Mostrar filtros.
16. Insira um valor de filtro "LCS" no campo "Nome do tipo" usando o operador de filtro "contém".
17. Clique em Abrir.
18. Na árvore, selecione 'Modelo de dados de amostra'.
    * Observe que você pode exibir uma avaliação das condições de pré-requisitos se foram satisfeitas para cada versão configurações de ER para o armazenamento atual. Para exibir esta previsão, clique em Verificar pré-requisitos.   
19. Clique em Verificar pré-requisitos.
20. Clique em Importar.
21. Clique em Sim.
22. Feche a página.
23. Feche a página.
24. Feche a página.
25. Vá para Administração da organização > Relatório eletrônico > Configurações.
26. Na árvore, expanda 'Modelo de dados de amostra'.
    * Observe que a configuração de mapeamento do modelo "Mapeamento de amostra" foi baixada com a configuração selecionada do modelo de dados. Os dois arquivos são baixados juntos porque o "Mapeamento de amostra" foi definido como implementação do modelo de dados selecionado e porque é aplicável ao aplicativo. A configuração "Mapeamento de amostra (alternativo)" não foi baixada porque a condição para a versão do aplicativo necessária não foi satisfeita.   
    * Se você se conectar ao Finance and Operations, registrar o mesmo provedor, acessar o mesmo projeto de LCS e baixar a mesma configuração do modelo de dados, a configuração "Mapeamento de amostra (alternativo)" será baixada, enquanto a configuração "Mapeamento de amostra" será ignorada.  


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]