--- 
title: "Criar uma configuração para importar dados de um arquivo externo no formato CSV (ER)"
description: "Use esse procedimento para criar configurações de ER (relatório eletrônico) para importar dados nos aplicativos Dynamics 365 for Finance and Operations de um arquivo externo no formato CSV."
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
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
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: f6bfa9f7c0638b0eaacf1a49bcd7d84ffab3acbf
ms.contentlocale: pt-br
ms.lasthandoff: 03/26/2018

---
# <a name="design-a-configuration-to-import-data-from-an-external-file-in-csv-format-er"></a>Criar uma configuração para importar dados de um arquivo externo no formato CSV (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Use esse procedimento para criar configurações de ER (relatório eletrônico) para importar dados nos aplicativos Dynamics 365 for Finance and Operations de um arquivo externo no formato CSV. Neste procedimento, você criará as configurações de ER necessárias para a empresa exemplo, Litware, Inc. Para concluir estas etapas, você deverá primeiramente concluir as etapas no procedimento, "ER Criar um provedor configuração e marcá-lo como ativo". 

Este procedimento é criado para usuários com a função atribuída de Administrador do sistema ou Desenvolvedor de relatório eletrônico. Estas etapas podem ser concluídas usando o conjunto de dados de USMF. 

Você também deve baixar e salvar localmente os seguintes arquivos: (https://go.microsoft.com/fwlink/?linkid=862266): 1099model.xml, 1099formatcsv.xml, 1099entriescsv.csv.

1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.
    * Você pode configurar um processo para importar arquivos externos em formato XML, TXT ou CSV para tabelas no aplicativo Dynamics 365 for Finance and Operations. Primeiro, você deve criar um modelo de dados abstrato para representar os dados importados, de um ponto de vista comercial, uma configuração do modelo de dados de ER é criada para isso. Em seguida, defina uma estrutura do arquivo importado que mapeie ao modelo de dados criado como forma de portar dados do arquivo ao modelo de dados abstrato, uma configuração de formato de ER é criada para isso. Depois, a configuração de modelo de dados de ER deve ser estendida com um novo mapeamento de modelo que descreva como os dados do arquivo importado e os dados persistentes do modelo de dados abstrato são usados para atualizar as tabelas do aplicativo ou entidades de dados.  
    * As etapas a seguir mostram como as transações de fornecedores externamente acompanhadas são importadas do arquivo CSV externo para uso posterior na liquidação de fornecedores para os formulários de 1099.   
    * Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como ativo. Se não visualizar esse provedor de configuração, você deve primeiro concluir as etapas do procedimento "Criar um provedor de configuração e marcá-lo como ativo".  
2. Clique em Configurações de relatórios.
3. Aplicar o filtro 'Modelo de pagamentos 1099'. Se já tiver concluído o procedimento “ER Criar as configurações necessárias para importar dados de um arquivo externo para relatório eletrônico” e a configuração 'Modelo de pagamentos 1099' estiver disponível na árvore de configuração, ignore todas as etapas da subtarefa a seguir.   

## <a name="add-a-new-er-model-configuration"></a>Adicionar uma nova configuração de modelo de ER
1. Em vez de criar um novo modelo para oferecer suporte à importação de dados, carregue o arquivo 1099model.xml, que foi baixado anteriormente. Este arquivo contém o modelo de dados personalizado das transações de fornecedores. Esse modelo de dados já está mapeado para os componentes de dados necessários.  
2. Clique em Trocar.
3. Clique em Carregar de um arquivo XML.
4. Clique em Procurar e navegue até o arquivo 1099model.xml que foi baixado anteriormente.  
5. Clique em OK.

## <a name="add-a-new-er-format-configuration-that-supports-data-import"></a>Adicione uma nova configuração de formato de ER que suporte importação de dados
1. Na árvore, selecione "Modelo de pagamento 1099".
2. Clique em Criar configuração para abrir a caixa de diálogo suspensa.
3. No campo Novo, insira "Formato baseado no modelo de dados do modelo de Pagamentos 1099".
4. Selecione Sim no campo Dá suporte à importação de dados.
5. Pressione a tecla ESC para fechar esta página.
    * Em vez de criar um novo formato de ER para oferecer suporte à importação de dados, carregue o arquivo 1099formatcsv.xml, que foi baixado anteriormente. Esse arquivo contém o formato de ER necessário que define a estrutura do arquivo CSV de entrada e o mapeamento dessa estrutura ao modelo de dados das transações de fornecedores.   
6. Clique em Trocar.
7. Clique em Carregar de um arquivo XML.
    * Clique em Procurar e navegue até o arquivo 1099formatcsv.xml, que foi baixado anteriormente.  
8. Clique em OK.
9. Na árvore, expanda "Modelo de pagamentos 1099".
10. Na árvore, selecione 'Modelo de pagamentos 1099\Para importar as transações de fornecedores (CSV)'.

## <a name="review-format-settings"></a>Examine as configurações de formato
1. Clique em Designer.
2. Clique em Expandir/recolher.
3. Ative 'Mostrar detalhes'.
    * O formato criado representa a estrutura prevista do arquivo externo no formato CSV.  
4. Na árvore, selecione 'Entrada: Arquivo\Raiz: Sequência'.
    * Para o elemento Raiz do tipo SEQUENCE, a opção 'Nova linha - Windows (CR LF)' foi selecionada no campo 'Caracteres especiais'. Com base nessa configuração, cada linha no arquivo de análise deve ser considerada como um registro separado.   
5. Na árvore, selecione 'Entrada: Arquivo\Raiz: Sequência\Linha: Sequência 1..* '.
    * Para o elemento Raiz\Linha do tipo SEQUENCE, a opção 'Um muitos' foi selecionada no campo 'Multiplicidade'. Com base nessa configuração, pelo menos uma linha será apresentada no arquivo de análise.   
6. Na árvore, selecione 'Entrada: Arquivo\Raiz: Sequência\Linha: Sequência 1..* Tipos: Caso'.
    * Observe que o elemento Raiz\Linha\Tipos do tipo CASE foi adicionado como o elemento aninhado da sequência Raiz\Linha. Como esse elemento CASE contém 3 elementos de sequência aninhados, essa configuração presume que esperamos atender a 3 tipos de linha diferentes no arquivo de análise.   
7. Na árvore, selecione 'Entrada: Arquivo\Raiz: Sequência\Linha: Sequência 1..* \Tipos: Caso\Cabeçalho: Sequência 1..1 '.
    * O elemento Raiz\Linha\Tipos\Cabeçalho do tipo SEQUENCE contém o elemento STRING aninhado cujo valor foi definido como o valor da cadeia de caracteres fixo. Esta sequência analisará a linha de cabeçalho do arquivo de análise.   
8. Na árvore, selecione 'Entrada: Arquivo\Raiz: Sequência\Linha: Sequência 1..* \Tipos: Caso\Registro: Sequência 1..1 (,)'.
    * O elemento Raiz\Linha\Tipos\Registro do tipo SEQUENCE foi configurado para analisar as linhas de transação. Observe que a opção de caracteres 'Delimitador personalizado' foi configurada como uma vírgula. Isso significa que a vírgula será usada como separador de campos para esse tipo de linha no arquivo de análise.   
    * Observe que vários elementos aninhados de diferentes tipos de dados foram adicionados ao elemento Raiz\Linha\Tipos\Registro para analisar as linhas de transação como campos separados. Observe que a opção 'Aplicativo de cotação' foi configurada como 'Nenhum'. Isso significa que no arquivo de análise, todos os campos desse tipo serão considerados como desprovidos de caracteres inseridos.   
9. Na árvore, selecione 'Entrada: Arquivo\Raiz: Sequência\Linha: Sequência 1..* \Tipos: Caso\Registro: Sequência 1..1 (,)\TransactionDate: DateTime'.
    * Por exemplo, o elemento Raiz\Linha\Tipos\Registro\TransactionDate do tipo DATETIME foi configurado para obter o valor de data e hora da transação a partir do arquivo de análise no formato 'M/d/aaaa'.   
10. Na árvore, selecione 'Entrada: Arquivo\Raiz: Sequência\Linha: Sequência 1..* \Tipos: Caso\Registro: Sequência 1..1 (,)\CountryCode: String 0..1 '.
    * Observe que o elemento Raiz\Linha\Tipos\Registro\CountryCode do tipo STRING foi configurado com a opção 'Zero um' no campo 'Multiplicidade'. Essa configuração considera o valor do campo CountryCode na linha de análise como opcional.   
11. Na árvore, selecione 'Entrada: Arquivo\Raiz: Sequência\Linha: Sequência 1..* \Tipos: Caso\Registro: Sequência 1..1 (,)\Comentário: Sequência 1..1 (,)'.
    * Observe que o elemento Raiz\Linha\Tipos\Registro\Comentário do tipo SEQUENCE foi configurado com a opção 'Tudo' no campo 'Aplicativo de cotação' e aspas duplas no campo 'Aspas'. Isso significa que todos os campos desse tipo de linhas no arquivo de análise (descrito pelos elementos aninhados: texto do tipo STRING) serão considerados como inseridos entre aspas duplas.  
12. Na árvore, selecione 'Entrada: Arquivo\Raiz: Sequência\Linha: Sequência 1..* \Tipos: Caso\Não analisado: Sequência 1..1 '.
    * O elemento Raiz\Linha\Tipos\Não analisado do tipo SEQUENCE foi configurado para analisar as linhas de transação da estrutura que não corresponde à estrutura descrita acima no elemento CASE pai.   

## <a name="review-the-setting-of-the-format-mapping-to-the-data-model"></a>Examine a configuração do mapeamento de formato para o modelo de dados
1. Clique em Mapear formato para modelo.
    * O mapeamento de modelo 'Mapeamento para modelo de formato CSV' descreve o fluxo de dados da transferência de dados do arquivo CSV de entrada ao modelo de dados.   
2. Clique em Designer.
3. Na árvore, expanda 'format'.
    * Observe que o formato criado será apresentado aqui como um componente de fonte de dados.  
4. Na árvore, expanda 'formato\Entrada: Arquivo(Incoming)'.
5. Na árvore, expanda 'formato\Entrada: Arquivo(Incoming)\Raiz: Sequência(Root)'.
6. Na árvore, expanda 'formato\Entrada: Arquivo(Incoming)\Raiz: Sequência(Root)\Linha: Sequência 1..* (Line)'.
7. Na árvore, expanda 'formato\Entrada: Arquivo(Incoming)\Raiz: Sequência(Root)\Linha: Sequência 1..* (Line)\Tipos: Caso(Types)'.
8. Na árvore, expanda 'formato\Entrada: Arquivo(Incoming)\Raiz: Sequência(Root)\Linha: Sequência 1..* (Line)\Tipos: Caso(Types)\Registro: Sequência 1..1 (,)(Record)'.
9. Na árvore, expanda 'formato\Entrada: Arquivo(Incoming)\Raiz: Sequência(Root)\Linha: Sequência 1..* (Line)\Tipos: Caso(Types)\Registro: Sequência 1..1 (,)(Record)\Dados'.
10. Na árvore, expanda 'formato\Entrada: Arquivo(Incoming)\Raiz: Sequência(Root)\Linha: Sequência 1..* (Line)\Tipos: Caso(Types)\Registro: Sequência 1..1 (,)(Record)\Dados\CountryCode: String 0..1 (CountryCode)'.
11. Na árvore, selecione 'formato\Entrada: Arquivo(Incoming)\Raiz: Sequência(Root)\Linha: Sequência 1..* (Line)\Tipos: Caso(Types)\Registro: Sequência 1..1 (,)(Record)\Dados\TransactionDate: DateTime(TransactionDate)'.
    * Observe que os elementos de formato obrigatórios e opcionais, como TransactionDate e CountryCode, têm um aspecto diferente no componente de fonte de dados de 'formato' predefinido.   
12. Na árvore, expanda 'Transações = '$both''.
    * Observe que os elementos do formato que define a estrutura do arquivo importado estão associados aos elementos do modelo de dados. Com base nessas associações, o conteúdo do arquivo CSV importado será armazenado no tempo de execução no modelo de dados existente. Preste atenção na associação do elemento CountryRegion. Para qualquer elemento de transação no arquivo de entrada que não tiver um valor de código de país especificado, o código de país padrão 'EUA' será preenchido no modelo de dados.   
13. Ative 'Mostrar detalhes'.
14. Clique na guia Validações.
15. Clique em Pesquisar.
16. No campo Encontrar, digite "forn.".
17. Clique em Localizar próximo.
    * Este mapeamento de formato pode conter a lógica definida pelo usuário para validar a precisão dos dados importados de um ponto de vista comercial. Por exemplo, com base na configuração, para qualquer linha no arquivo de importação cuja estrutura não corresponda nem à estrutura da linha de cabeçalho nem a da linha de transação, uma mensagem de aviso será gerada no Log de Informações comunicando o usuário sobre esse caso, indicando o número de sequência da transação no arquivo.   
18. Feche a página.

## <a name="run-the-format-mapping"></a>Executar o mapeamento de formato
Para fins de teste, execute o mapeamento de formato usando o arquivo 1099entriescsv.csv, que foi baixado anteriormente. A saída gerada apresentará os dados que serão importados do arquivo CSV selecionado e preenchidos no modelo de dados personalizado na importação real.   
1. Clique em Executar.
    * Clique em Procurar e navegue até o arquivo 1099entriescsv.csv, que foi baixado anteriormente.  
2. Clique em OK.
    * Observe as mensagens de aviso sobre as linhas que não são aceitas. A linha 4 contém o valor da renda que é apresentado no formato não aceitável enquanto a linha 7 não contém o texto do comentário de transação em aspas duplas.   
    * Examine a saída no formato XML, que representa os dados que foram importados do arquivo selecionado e transferidos para o modelo de dados. Observe que todas as 7 linhas do arquivo CSV importado foram processadas. A linha 1 dos títulos de campos foi ignorada, 4 transações foram devidamente analisadas e 2 transações foram reconhecidas como inválidas.   
3. Feche a página.
4. Feche a página.


