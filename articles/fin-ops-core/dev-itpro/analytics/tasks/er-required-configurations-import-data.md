---
title: ER Criar configurações necessárias para importar os dados de um arquivo externo
description: Este tópico descreve como criar configurações de ER (relatório eletrônico) para importar dados para o aplicativo do Microsoft Dynamics 365 Finance de um arquivo externo.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERSolutionCreateDropDialog, EROperationDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula, Tax1099Summary, VendSettlementTax1099
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1b8a94173c7c5367b79bfcb354f0397515d94445
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564281"
---
# <a name="er-create-required-configurations-to-import-data-from-an-external-file"></a>ER Criar configurações necessárias para importar os dados de um arquivo externo

[!include [banner](../../includes/banner.md)]

As etapas a seguir explicam como um usuário na função de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar configurações de relatório eletrônico (ER) para importar dados para o aplicativo, partindo de um arquivo externo. Neste exemplo, você criará as configurações de ER necessárias para a empresa exemplo, Litware, Inc. Para concluir estas etapas, você deverá primeiramente concluir as etapas no Guia da tarefas, "ER Criar um provedor configuração" e marcá-lo como ativo. Estas etapas podem ser concluídas usando o conjunto de dados de USMF. Você também deve baixar e salvar os seguintes arquivos localmente usando os links do tópico da visão geral do Relatório eletrônico (https://go.microsoft.com/fwlink/?linkid=852550): 1099model.xml, 1099format.xml, 1099entries.xml e 1099entries.xlsx.

O ER oferece aos usuários de negócios a capacidade de configurar o processo de importação de arquivos de dados externos para tabelas no formato .XML ou .TXT. Primeiramente, um modelo de dados abstrato e uma configuração do modelo de dados de ER devem ser criados para representar os dados que você está importando. Em seguida, você precisa definir a estrutura do arquivo que você está importando e o método que usará para transferir os dados do arquivo para modelo de dados abstrato. A configuração de formato de ER que é mapeada ao modelo de dados criado deve ser criada para esse modelo de dados abstrato. Depois, a configuração do modelo de dados deve ser estendida com um mapeamento que descreve como os dados importados persistem como dados do modelo de dados abstratos e como são usados para atualizar as tabelas.  A configuração do modelo de dados de ER deve ser acrescentada com um novo mapeamento de modelo que descreve a associação do modelo de dados a destinos do aplicativo.  

O cenário a seguir mostra os recursos da importação de dados de ER. Isso inclui transações do fornecedor que são rastreadas externamente e depois importadas para serem relatadas posteriormente na liquidação do fornecedor para impostos 1099.   

## <a name="add-a-new-er-model-configuration"></a>Adicionar uma nova configuração de modelo de ER
1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.

    Verifique se o provedor de configuração para a empresa exemplo "Litware, Inc." está disponível e marcado como ativo. Se não visualizar este provedor de configuração, você deve primeiro concluir as etapas do procedimento "Criar um provedor de configuração e marcá-lo como ativo".   

2. Clique em Configurações de relatórios.

    Em vez de criar um novo modelo para oferecer suporte à importação de dados, carregue o arquivo, 1099model.xml, que foi baixado anteriormente. Este arquivo contém o modelo de dados personalizado das transações de fornecedores. Esse modelo de dados é mapeado para os componentes de dados que estão na entidade de dados da AOT.   

3. Clique em Trocar.
4. Clique em Carregar de um arquivo XML.

    Clique em Procurar e navegue até o arquivo 1099model.xml que foi baixado anteriormente.  

5. Clique em OK.
6. Na árvore, selecione "Modelo de pagamento 1099".

## <a name="review-data-model-settings"></a>Examine as configurações do modelo de dados
1. Clique em Designer.

    Esse modelo é criado para representar as transações de fornecedores do ponto de vista comercial e é separado da implementação.   

2. Na árvore, expanda "1099-MISC".
3. Na árvore, selecione "1099-MISC\Transações".
4. Na árvore, expanda "1099-MISC\Transações".

    O elemento Transações deste modelo representa transações individuais. Os elementos filho são usados para especificar os detalhes necessários, como a conta de fornecedor e data de transação, para cada transação.   

5. Feche a página.

## <a name="add-a-new-er-format-configuration-that-supports-data-import"></a>Adicione uma nova configuração de formato de ER que suporte importação de dados
As etapas nesta subtarefa mostram como uma nova configuração de formato pode ser criada para gerenciar a importação de dados de arquivos externos.   
1. Clique em Criar configuração para abrir a caixa de diálogo suspensa.
2. No campo Novo, insira "Formato baseado no modelo de dados do modelo de Pagamentos 1099".
3. Selecione Sim no campo Dá suporte à importação de dados.
4. Pressione a tecla ESC para fechar esta página.

    Em vez de criar um novo formato para oferecer suporte à importação de dados, carregue o arquivo, 1099format.xml, que foi baixado anteriormente. Este arquivo contém a estrutura definida do arquivo que você está importando e o mapeamento da estrutura do modelo de dados personalizado de transações de fornecedores.   
5. Clique em Trocar.
6. Clique em Carregar de um arquivo XML.
    Clique em Procurar e navegue até o arquivo 1099format.xml que foi baixado anteriormente.  
7. Clique em OK.
8. Na árvore, expanda "Modelo de pagamentos 1099".
9. Na árvore, selecione as transações "Modelo de pagamentos 1099\Formato de importação de fornecedores".

## <a name="review-format-settings"></a>Examine as configurações de formato
1. Clique em Designer.
2. Ative "Mostrar detalhes".
3. Clique em Expandir/recolher.
4. Clique em Expandir/recolher.

    O formato criado representa a estrutura prevista do arquivo externo. Esse arquivo deve estar no formato XML e ter o elemento raiz de liquidação. Cada transação do fornecedor é representada pelo elemento da transação que é definido como tendo a multiplicidade zero para muitos. Isso significa que o arquivo de entrada pode conter de zero a várias transações. Os elementos aninhados do elemento "transação" representam os atributos de uma única transação. Observe que todos os atributos, exceto o país, estão marcados como obrigatórios, o que significa que é necessário tê-los no arquivo de importação.   

## <a name="review-the-settings-of-the-format-mapping-to-the-data-model"></a>Revise as configurações do mapeamento de formato para o modelo de dados
1. Clique em Mapear formato para modelo.

    O mapeamento "Para importar as transações de fornecedores" contém as regras de transferência de dados do arquivo XML de entrada para a parte selecionada do modelo de dados personalizado, que é estabelecido na definição 1099-MISC.  

2. Clique em Designer.
3. Ative "Mostrar detalhes".
4. Na árvore, expanda "formato: Registro".
5. Na árvore, selecione "formato: Registro".

    Observe que o formato criado será apresentado aqui como um componente de fonte de dados.  

6. Na árvore, expanda `format: Record\*settlement: XML Element 1..1 (settlement): Record`.
7. Na árvore, expanda `format: Record\*settlement: XML Element 1..1 (settlement): Record\transaction: XML Element 0..* (transaction): Record list`.
8. Na árvore, expanda `format: Record\*settlement: XML Element 1..1 (settlement): Record\transaction: XML Element 0..* (transaction): Record list\*vendor: XML Element 1..1 (vendor): Record`.
9. Na árvore, expanda `format: Record\*settlement: XML Element 1..1 (settlement): Record\transaction: XML Element 0..* (transaction): Record list\country: XML Element 0..1 (country): Record`.
10. Na árvore, selecione `format: Record\*settlement: XML Element 1..1 (settlement): Record\transaction: XML Element 0..* (transaction): Record list\*vendor: XML Element 1..1 (vendor): Record`.

    Observe que a apresentação de elementos obrigatórios e opcionais de formato é diferente no componente da fonte de dados do "formato" predefinido.  
11. Na árvore, expanda "Transações: Lista de registros = format.settlement.'$enumerated''.

    Observe que os elementos de formato que definem a estrutura do arquivo importado estão associados aos elementos do modelo de dados personalizado. Com base nessas associações, o conteúdo do arquivo XML importado será armazenado no tempo de execução no modelo de dados existente. Preste atenção na associação do elemento do país. Para qualquer elemento de transação no arquivo de entrada que não tenha esse elemento, o código de país padrão "EUA" será preenchido no modelo de dados.  

12. Clique na guia Validações.

    Este mapeamento de formato pode conter a lógica definida pelo usuário para validar a precisão dos dados importados de um ponto de vista comercial. Por exemplo, com base na configuração, como em qualquer transação no arquivo importado sem um código de país definido, uma mensagem de aviso será gerada no Log de Informações informando ao usuário sobre o caso e indicando o número de sequência da transação.  

13. Feche a página.

## <a name="run-the-format-mapping-to-the-data-model"></a>Execute o mapeamento de formato para o modelo de dados
Execute este mapeamento de formato para fins de teste. Use o arquivo 1099entries.xml que foi baixado anteriormente. Você pode exportar este arquivo da pasta de trabalho 1099entries.xlsx que foi usada para gerenciar transações do fornecedor. A saída gerada será importada do arquivo XML selecionado e preencherá o modelo de dados personalizado na importação real.  

1. Clique em Executar.

    Clique em Procurar e navegue até o arquivo 1099entries.xml que foi baixado anteriormente.  

2. Clique em OK.

    Observe a mensagem de aviso sobre um código de país ausente para uma transação no arquivo importado.  
    
    Revise a saída no formato XML, que representa os dados que foram importados do arquivo selecionado e transferidos para o modelo de dados.   

3. Feche a página.
4. Feche a página.

## <a name="review-the-settings-for-the-model-mapping-to-the-destinations"></a>Revise as configurações do mapeamento de modelo para os destinos
1. Na árvore, selecione "Modelo de pagamento 1099".
2. Clique em Designer.
3. Clique em Mapear modelo para fonte de dados.

    O mapeamento para importação de transações manuais 1099 foi definido com o tipo de direção de destino Até. Isso significa que ele foi inserido para oferecer suporte à importação de dados e contém a configuração de regras que definem como o arquivo externo importado e persistente como dados do modelo de dados abstratos é usado para atualizar tabelas no aplicativo.  

4. Clique em Designer.
5. Na árvore, expanda "modelo: Modelo de dados do modelo de Pagamentos 1099".
6. Na árvore, expanda "modelo: Modelo de dados do modelo de Pagamentos 1099\Transações: Lista de registros".

    Observe que o modelo criado será apresentado aqui como um elemento da fonte de dados. No tempo de execução, ele conterá os dados importados do arquivo externo. Várias tabelas foram adicionadas como os elementos da fonte de dados para garantir que os dados importados estejam compatíveis com os dados do aplicativo atual, incluindo se a conta de fornecedor da transação de importação está disponível no sistema, se a combinação de país de importação e códigos de estado existe etc  

7. Na árvore, selecione 'modelo: Modelo de dados do Modelo de pagamentos 1099\Transações: falha da Lista de registros\$: Campo calculado = IF(OR(ISEMPTY(model.Transactions.'$refs'.vendor), ISEMPTY(model.Transactions.'$refs'.vendor1099), ISEMPTY(model.Transactions.'$refs'.box1099), ISEMPTY(model.Transactions.'$refs'.country), ISEMPTY(model.Transactions.'$refs'.state), ISEMPTY(model.Transactions.'$refs'.location)), true, false): Booliano'.
8. Clique em Editar.
9. Clique em Editar fórmula.

    Quando pelo menos uma validação falha para uma única transação importada, esta transação será marcada como falha pelo atributo de fonte de dados "$failed".  

10. Feche a página.
11. Clique em Cancelar.
12. Na árvore, selecione "tax1099trans: Tabela "VendSettlementTax1099" registros= model.Validated".
13. Clique em Editar destino.

    Este destino de ER foi adicionado para especificar como os dados importados atualizarão as tabelas do aplicativo. Nesse caso, a tabela de dados VendSettlementTax1099 foi selecionada. Como a ação de registro Inserir foi marcada, as transações importadas serão inseridas na tabela VendSettlementTax1099. Observe que um mapeamento de modelo único pode conter vários destinos. Isso significa que os dados importados podem ser usados para atualizar várias tabelas do aplicativo de uma vez. As tabelas, as exibições e as entidades de dados podem ser usadas como destinos de ER.   

    Se o mapeamento será chamado de um ponto do aplicativo (como um botão ou item de menu) que foi criado especificamente para esta ação, o destino de ER deve ser marcado como o ponto de integração. Neste exemplo, este é o ponto de ERTableDestination#VendSettlementTax1099.  

14. Clique em Cancelar.
15. Clique em Mostrar tudo.
16. Clique em Mostrar somente mapeado.
17. Na árvore, expanda "tax1099trans: Tabela "VendSettlementTax1099" registros= model.Validated".

    Observe que o elemento da fonte de dados que contém as únicas transações validadas está associado ao destino criado. Você pode filtrar as transações importadas para ignorar aquelas que são incompatíveis com os dados dos aplicativos.  

18. Na árvore, selecione "falha: Tabela "VendSettlementTax1099Entity" registros= model.Failed".
19. Clique na guia Validações.

    Este mapeamento de modelo pode conter a lógica definida pelo usuário para validar a exatidão dos dados importados dos dados do aplicativo existentes. Por exemplo, com base na configuração atual, para qualquer transação no arquivo importado com uma conta de fornecedor que não está no sistema, uma mensagem de aviso será gerada, informando ao usuário e indicando o código de conta do fornecedor incorreto.  

    Observe que a opção de ação pós-validação pode ser usada para cada validação, para especificar se o processo de importação deve ser continuado ou interrompido, bem como se as inserções/atualizações já realizadas podem ser mantidas ou revertidas.  

20. Clique em Mostrar somente mapeado.
21. Clique em Mostrar tudo.
22. Feche a página.

    Execute este mapeamento de modelo para testar o formato criado os mapeamentos de modelo. Use o arquivo 1099entries.xml. Os dados do arquivo selecionado serão importados no sistema.  

23. Clique em Executar.

    Observe que a caixa de diálogo não contém perguntas adicionais sobre o mapeamento de formato que deve ser usado para analisar o arquivo importado e, em seguida, transferir os dados para o modelo de dados. Isso ocorre porque há somente um formato que usa este modelo, o que é marcado como criado para dar suporte à importação de dados.  
    
    Defina a ID de comprovante para diferenciar as transações importadas de outras transações que já tenham sido inseridas manualmente ou importadas.  

24. No campo Inserir id do comprovante, digite "IMPORT-001".

    Navegue para obter o arquivo "1099entries.xml".  

25. Clique em OK.

    A lista de avisos gerados fornece informações sobre contas incorretas de fornecedores, um código incorreto de caixa imposto 1099, os códigos de país ausentes, etc. Compare essa lista de avisos ao conteúdo que está incluído no arquivo XML em execução.  

26. Feche a página.
27. Feche a página.
28. Feche a página.
29. Feche a página.
30. Vá para Contas a pagar > Tarefas periódicas > Imposto 1099 > Liquidação de fornecedor para impostos 1099.

    Este formulário mostra as transações cumulativas na tabela de Tax1099Summary criadas com base nas transações importadas.  

31. No campo Data inicial, defina a data como '01-01-2000'.
32. Clique em Transações 1099 manuais.

    Este formulário contém a lista de transações que foram adicionadas manualmente as que apenas foram importadas.  

33. Abra o filtro da coluna do Comprovante.
34. Insira um valor de filtro de "IMPORT-001" no campo "Comprovante" usando o operador de filtro "começa com".

## <a name="review-the-relationship-between-model-and-format-mappings"></a>Revise o relacionamento entre os mapeamentos de modelo e de formato
1. Feche a página.
2. Feche a página.
3. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.
4. Clique em Configurações de relatórios.
5. Na árvore, selecione "Modelo de pagamento 1099".

    Suponha que deseja dar suporte à importação dos mesmos dados, mas de um formato de arquivo .TXT.   

6. Clique em Criar configuração para abrir a caixa de diálogo. 
7. No campo Novo, insira "Formato baseado no modelo de dados do modelo de Pagamentos 1099".
8. No campo Nome, digite "Importar dados do arquivo TXT".
9. Selecione Sim no campo Dá suporte à importação de dados.
10. Clique em Criar configuração.
11. Clique em Designer.
12. Clique em Mapear formato para modelo.
13. Clique em Novo.
14. No campo Definição, insira ou selecione um valor.

    Selecione a opção "1099-MISC".  

15. No campo Nome, digite "Importar dados do arquivo TXT".
16. No campo Descrição, digite "Importar dados do arquivo TXT".
17. Clique em Salvar.
18. Feche a página.
19. Feche a página.
20. Clique em Editar.

    Se você instalou o hotfix "KB 4012871 Suporte de mapeamentos de modelo de GER em configurações separadas com uma capacidade de especificar diferentes tipos de pré-requisitos para implantar em diferentes versões do Dynamics 365 Finance" ([KB 4012871](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871)), execute a próxima etapa "Ativar o sinalizador 'Padrão do mapeamento de modelo'" para a configuração de formato inserida. Caso contrário, ignore a próxima etapa.  

21. Selecione Sim no campo Padrão do mapeamento de modelo.
22. Na árvore, selecione "Modelo de pagamento 1099".
23. Clique em Designer.
24. Clique em Mapear modelo para fonte de dados.
25. Clique em Executar.

    Se você instalou o hotfix KB 4012871 Suporte de mapeamentos de modelo de GER em configurações separadas com uma capacidade de especificar diferentes tipos de pré-requisitos para implantar em diferentes versões do ([KB 4012871](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871)), selecione o mapeamento de modelos preferencial no campo de pesquisa. Se você não tiver instalado o hotfix ainda, vá para a etapa seguinte, pois o mapeamento já foi selecionado pela definição da configuração do formato padrão.  
    
    Se você não tiver instalado o hotfix, o KB 4012871, observe que a caixa de diálogo contém uma pergunta de mapeamento do modelo adicional que é usada para analisar o arquivo que você está importando. Em seguida, os dados são transferidos da caixa de diálogo para o modelo de dados. Atualmente, você pode escolher qual mapeamento de formato deve ser usado, dependendo do tipo de arquivo que você pretende importar.  
    
    Se você pretende chamar este mapeamento de modelos, partindo de um ponto no aplicativo que é criado especificamente para a ação, o destino de ER e o mapeamento do formato devem ser marcados como parte da integração.  

26. Clique em Cancelar.
27. Feche a página.
28. Feche a página.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]