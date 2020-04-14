---
title: Gerenciar o mapeamento do modelo de ER em configurações de ER separadas
description: As etapas a seguir explicam como um usuário atribuído ao Administrador do sistema ou Desenvolvedor de relatório eletrônico pode gerenciar mapeamentos de modelo de Relatório eletrônico (RE) em configurações de ER separadas.
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
ms.openlocfilehash: b8ff3b419caafec626497c65ea18ca24ca95cb5d
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143044"
---
# <a name="manage-er-model-mapping-in-separate-er-configurations"></a>Gerenciar o mapeamento do modelo de ER em configurações de ER separadas

[!include [banner](../../includes/banner.md)]

As etapas a seguir explicam como um usuário atribuído ao Administrador do sistema ou Desenvolvedor de relatório eletrônico pode gerenciar mapeamentos de modelo de Relatório eletrônico (RE) em configurações de ER separadas. Nesta guia de tarefas, você criará as configurações de ER necessárias para a empresa exemplo, Litware, Inc. Para concluir este guia de tarefas, você deverá primeiramente concluir as etapas no guia de tarefas, "ER Criar um provedor configuração" e marcá-lo como ativo. 

Como as configurações de ER são compartilhadas entre empresas, você pode concluir este guia de tarefas usando o conjunto de dados da empresa de sua escolha. A funcionalidade deste guia de tarefas estará disponível se você tiver instalado um dos seguintes hotfixes: https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012872 para a versão 7.0 do Dynamics AX ou https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871 para a versão Dynamics 365 for Operations.

1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.
    * Verifique se o provedor de configuração para a empresa exemplo Litware, Inc. está disponível e marcado como ativo. Se não visualizar este provedor de configuração, você deverá concluir primeiro as etapas na guia de tarefas, Criar um provedor de configuração e marcá-lo como ativo.   

## <a name="add-a-new-er-model-configuration"></a>Adicionar uma nova configuração de modelo de ER
1. Clique em Configurações de relatórios.
    * Adicionar uma nova configuração de modelo. O nome deve ser exclusivo na árvore de configurações.  
2. Clique em Criar configuração para abrir a caixa de diálogo suspensa.
3. No campo Nome, digite "Modelo de dados de amostra".
    * Modelo de dados de exemplo  
4. Clique em Criar configuração.
5. Clique em Designer.
6. Clique em Novo para abrir a caixa de diálogo suspensa.
7. No campo Nome, digite "Raiz".
    * Raiz  
8. Clique em Adicionar.
9. Clique em Novo para abrir a caixa de diálogo suspensa.
10. No campo Nome, digite 'Empresa'.
    * Empresa  
11. Clique em Adicionar.
12. No campo Descrição, insira o texto, a descrição da entidade legal ou da empresa em que o usuário fez logon no tempo de execução. 
    * Descrição da entidade legal ou da empresa em que o usuário fez logon no tempo de execução.  
13. Clique em Referência raiz.
14. Clique em OK.
15. Clique em Salvar.
16. Feche a página.
17. Clique em Alterar status.
18. Clique em Concluir.
19. Clique em OK.

## <a name="add-a-new-er-model-mapping-configuration"></a>Adicionar uma nova configuração de mapeamento do modelo de ER
1. Clique em Criar configuração para abrir a caixa de diálogo suspensa.
2. No campo Novo, insira 'Mapeamento de modelo baseado no modelo de dados Modelo de dados de amostra'.
3. No campo Nome, digite 'Mapeamento de amostra'.
    * Mapeamento de amostra  
4. Clique em Criar configuração.
5. Expanda a seção Pré-requisitos.
    * Observe que o grupo de pré-requisitos Implementações foi adicionado automaticamente. O grupo contém o componente de pré-requisito que se refere à configuração do modelo de dados pai e é marcado como Implementação. Isso significa que esta Configuração de mapeamento do modelo de mapeamento de amostra é considerada a implementação do modelo de dados Modelo de dados de amostra. Portanto, este componente forçará o ER para baixar a configuração de mapeamento do modelo Mapeamento de amostra de um repositório de ER sempre que a configuração do modelo Modelo de dados de amostra for baixada.   
6. Clique em Designer.
    * Observe que a configuração de mapeamento modelo criada contém um novo mapeamento em branco com o mesmo nome da configuração criada. Lembre-se que quando uma configuração de modelo pai selecionada contiver mapeamentos de modelo, eles serão copiados para uma configuração de mapeamento do novo modelo.   
7. Clique em Designer.
8. Na árvore, selecione 'Dynamics 365 for Operations\Tabela'.
9. Clique em Adicionar raiz.
10. No campo Nome, digite 'Empresa'.
    * Empresa  
11. No campo Tabela, digite 'CompanyInfo'.
    * CompanyInfo  
12. Clique em OK.
13. Na árvore, expanda 'Empresa'.
14. Na árvore, expanda 'Empresa\find()'.
15. Na árvore, selecione 'Empresa\find()\Nome'.
16. Clique em Associar.
17. Clique em Salvar.
18. Feche a página.
19. Feche a página.
20. No Painel de Ação, clique em Configurações.
21. Clique em Parâmetros de usuário.
22. Selecione Sim no campo Executar configurações.
23. Clique em OK.
24. Clique em Editar.
25. Selecione Sim no campo Executar Rascunho.

## <a name="add-a-new-er-format-configuration"></a>Adicionar uma nova configuração de formato de ER
1. Na árvore, selecione 'Modelo de dados de amostra'.
2. Clique em Criar configuração para abrir a caixa de diálogo suspensa.
3. No campo Novo, insira 'Formato baseado no modelo de dados Modelo de dados de amostra'.
4. No campo, digite 'Formato de amostra'.
    * Formato de amostra  
5. Clique em Criar configuração.
6. Clique em Designer.
7. Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.
8. Na árvore, selecione 'Texto\Cadeia de caracteres'.
9. Clique em OK.
10. Clique na aba Mapeamento.
11. Na árvore, expanda 'modelo'.
12. Na árvore, selecione 'modelo\Empresa'.
13. Clique em Associar.
14. Clique em Salvar.
15. Feche a página.
    * Executar a versão de rascunho de formato criado para fins de teste.  
16. Clique em Executar.
    * Em versões FastTab, clique em Executar.  
17. Clique em OK.
    * Reveja a saída que contêm o nome da empresa na qual o usuário que está executando essa configuração de formato está registrado. Observe que a configuração de mapeamento modelo criada será usada por essa configuração de formato porque só há uma configuração disponível que contém mapeamentos de modelo necessários.   

## <a name="add-alternative-er-model-mapping-configuration"></a>Adicionar a configuração de mapeamento do modelo de ER alternativo
1. Na árvore, selecione 'Modelo de dados de amostra'.
2. Clique em Criar configuração para abrir a caixa de diálogo suspensa.
3. No campo Novo, insira 'Mapeamento de modelo baseado no modelo de dados Modelo de dados de amostra'.
4. No campo Nome, digite "Mapeamento de amostra (alternativo)'.
    * Mapeamento de amostra (alternativo)  
5. Clique em Criar configuração.
6. Clique em Designer.
7. Clique em Designer.
8. Na árvore, selecione 'Dynamics 365 for Operations\Tabela'.
9. Clique em Adicionar raiz.
10. No campo Nome, digite 'Empresa'.
    * Empresa  
11. No campo Tabela, digite 'CompanyInfo'.
    * CompanyInfo  
12. Clique em OK.
13. Clique em Editar.
14. Na árvore, selecione 'Cadeia de caracteres\CONCATENATE'.
15. Clique em Adicionar função.
16. Na árvore, expanda 'Empresa'.
17. Na árvore, expanda 'Empresa\find()'.
18. Na árvore, selecione 'Empresa\find()\Nome'.
19. Clique em Adicionar fonte de dados.
20. No campo Fórmula, digite um valor.
    * CONCATENATE(Company.'find()'.Name, ";",  
21. Na árvore, selecione 'Company\find()\Company(DataArea)'.
22. Clique em Adicionar fonte de dados.
23. No campo Fórmula, digite um valor.
    * CONCATENATE(Company.'find()'.Name, ";", Company.'find()'.DataArea)  
24. Clique em Salvar.
25. Feche a página.
26. Clique em Salvar.
27. Feche a página.
28. Feche a página.
29. Selecione Sim no campo Executar Rascunho.

## <a name="use-an-existing-er-model-mapping-configuration"></a>Usar uma configuração existente de mapeamento do ER
1. Na árvore, selecione "Modelo de dados de amostra\Formato de amostra".
2. Clique em Executar.
    * Observe que a versão de rascunho selecionada da configuração de formato de ER não pode ser realizada porque há mais de uma configuração de mapeamento de modelo disponível para o modelo de dados indefinido que foi selecionada como a fonte de dados do formato de ER de execução.   
    * Em seguida, você definirá a configuração de mapeamento de modelo alternativo como aquela da qual os mapeamentos modelo serão usados como fontes de dados do formato de ER de execução.   
3. Na árvore, selecione "Modelo de dados de amostra\Mapeamento de amostra (alternativo)".
4. Selecione Sim no campo Padrão do mapeamento de modelo.
5. Na árvore, selecione "Modelo de dados de amostra\Formato de amostra".
6. Clique em Executar.
7. Clique em OK.
    * Observe que a configuração de mapeamento de modelo padrão será usada por essa configuração de formato para gerar o documento eletrônico (a saída criada contêm o código da empresa).  

