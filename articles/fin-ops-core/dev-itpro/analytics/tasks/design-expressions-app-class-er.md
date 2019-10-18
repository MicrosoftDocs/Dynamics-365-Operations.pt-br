---
title: Criar expressões de ER para chamar métodos de classe de aplicativo
description: Este guia fornece informações sobre como reutilizar a lógica de aplicativo existente em configurações de ER (relatório eletrônico) chamando métodos necessários de classes de aplicativos em expressões de ER.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
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
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f61228d328521d0c6fe8e0ae704001a65d03151f
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249218"
---
# <a name="design-er-expressions-to-call-application-class-methods"></a>Criar expressões de ER para chamar métodos de classe de aplicativo

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este guia fornece informações sobre como reutilizar a lógica de aplicativo existente em configurações de ER (relatório eletrônico) chamando métodos necessários de classes de aplicativos em expressões de ER. Os valores de argumentos para chamar classes podem ser definidos dinamicamente no tempo de execução: por exemplo, com base em informações no documento de análise para garantir sua exatidão. Neste guia, você criará as configurações de ER necessárias para a empresa de exemplo, Litware, Inc. Esse procedimento é criado para usuários com a função atribuída de Administrador de sistema ou Desenvolvedor de relatório eletrônico. 

Estas etapas podem ser concluídas usando qualquer conjunto de dados. Você também deve baixar e salvar o próximo arquivo localmente: (https://go.microsoft.com/fwlink/?linkid=862266): SampleIncomingMessage.txt.

Para concluir essas etapas, você deve primeiro concluir as etapas do procedimento “ER Criar um provedor de configuração e marcá-lo como ativo“.

1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.
    * Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como ativo. Se não visualizar esse provedor de configuração, você deve primeiro concluir as etapas do procedimento "Criar um provedor de configuração e marcá-lo como ativo".   
    * Você está criando um processo para analisar extratos bancários de entrada para uma atualização de dados do aplicativo. Você receberá os extratos bancários de entrada como arquivos TXT que contêm códigos IBAN. Como parte do processo de importação do extrato bancário, você precisa validar a exatidão desses códigos IBAN usando a lógica que já está disponível.   

## <a name="import-a-new-er-model-configuration"></a>Importar uma nova configuração de modelo de ER
1. Na lista, localize e selecione o registro desejado.
    * Selecione o bloco do provedor Microsoft.  
2. Clique em Repositórios.
3. Clique em Mostrar filtros.
4. Adicionar um campo de filtro 'Nome do tipo'. No campo Nome, digite o valor “recursos”, selecione o operador de filtro "contém" e clique em Aplicar.
5. Clique em Abrir.
6. Na árvore, selecione 'Modelo de pagamento'.
    * Se o botão Importar na Guia Rápida Versões não estiver habilitado, você já importou a versão 1 da configuração de ER 'Modelo de pagamento'. Você pode ignorar as etapas restantes nesta subtarefa.   
7. Clique em Importar.
8. Clique em Sim.
9. Feche a página.
10. Feche a página.

## <a name="add-a-new-er-format-configuration"></a>Adicionar uma nova configuração de formato de ER
1. Clique em Configurações de relatórios.
    * Adicionar um novo formato de ER para analisar extratos bancários de entrada no formato TXT.  
2. Na árvore, selecione 'Modelo de pagamento'.
3. Clique em Criar configuração para abrir a caixa de diálogo do menu.
4. No campo Novo, insira 'Formato baseado no modelo de dados PaymentModel'.
5. No campo Nome, digite 'Formato de importação de extrato bancário (exemplo)'.
    * Formato de importação de extrato bancário (exemplo)  
6. Selecione Sim no campo Dá suporte à importação de dados.
7. Clique em Criar configuração.

## <a name="design-the-er-format-configuration---format"></a>Criar a configuração de formato de ER - formato
1. Clique em Designer.
    * O formato criado representa a estrutura prevista do arquivo externo no formato TXT.  
2. Clique em Adicionar raiz para abrir a caixa de diálogo do menu.
3. Na árvore, selecione 'Texto\Sequência'.
4. No campo Nome, digite "Raiz".
    * Raiz  
5. No campo Caracteres especiais, selecione 'Nova linha - Windows (CR LF)'.
    * A opção 'Nova linha - Windows (CR LF)' foi selecionada no campo 'Caracteres especiais'. Com base nessa configuração, cada linha no arquivo de análise é considerada um registro separado.  
6. Clique em OK.
7. Clique em Adicionar para abrir a caixa de diálogo suspensa.
8. Na árvore, selecione 'Texto\Sequência'.
9. No campo Nome, digite 'Linhas'.
    * Linhas  
10. No campo Multiplicidade, selecione 'Um muitos'.
    * A opção 'Um muitos' foi selecionada no campo 'Multiplicidade'. Com base nessa configuração, espera-se que pelo menos uma linha seja apresentada no arquivo de análise.  
11. Clique em OK.
12. Na árvore, selecione 'Raiz\Linhas'.
13. Clique em Adicionar sequência.
14. No campo Nome, digite 'Campos'.
    * Campos  
15. No campo Multiplicidade, selecione 'Exatamente um'.
16. Clique em OK.
17. Na árvore, selecione 'Raiz\Linhas\Campos'.
18. Clique em Adicionar para abrir a caixa de diálogo suspensa.
19. Na árvore, selecione 'Texto\Cadeia de caracteres'.
20. No campo Nome, digite 'IBAN'.
    * IBAN  
21. Clique em OK.
    * Configurou-se que cada linha no arquivo de análise contém o único código IBAN.  
22. Clique em Salvar.

## <a name="design-the-er-format-configuration--mapping-to-data-model"></a>Criar a configuração de formato de ER – mapeamento para modelo de dados
1. Clique em Mapear formato para modelo.
2. Clique em Novo.
3. No campo Definição, digite 'BankToCustomerDebitCreditNotificationInitiation'.
    * BankToCustomerDebitCreditNotificationInitiation  
4. Resolver altera a definição.
5. No campo Nome, digite 'Mapeamento para modelo de dados'.
    * Mapeamento para modelo de dados  
6. Clique em Salvar.
7. Clique em Designer.
8. Na árvore, selecione 'Dynamics 365 for Operations\Classe'.
9. Clique em Adicionar raiz.
    * Adicionar uma nova fonte de dados para chamar a lógica de aplicativo existente para validação de códigos IBAN.  
10. No campo Nome, digite 'check_codes'.
    * check_codes  
11. No campo Classe, digite 'ISO7064'.
    * ISO7064  
12. Clique em OK.
13. Na árvore, expanda 'format'.
14. Na árvore, expanda 'formato\Raiz: Sequência(Root)'.
15. Na árvore, selecione 'formato\Raiz: Sequência(Root)\Linhas: Sequência 1..* (Rows)'.
16. Clique em Associar.
17. Na árvore, expanda 'formato\Raiz: Sequência(Root)\Linhas: Sequência 1..* (Rows)'.
18. Na árvore, expanda 'formato\Raiz: Sequência(Root)\Linhas: Sequência 1..* (Rows)\Campos: Sequência 1..1 (Fields)'.
19. Na árvore, selecione 'formato\Raiz: Sequência(Root)\Linhas: Sequência 1..* (Rows)\Campos: Sequência 1..1 (Fields)\IBAN: String(IBAN)'.
20. Na árvore, expanda 'Pagamentos = format.Root.Rows'.
21. Na árvore, expanda 'Pagamentos = format.Root.Rows\Conta do Credor(CreditorAccount)'.
22. Na árvore, expanda 'Pagamentos = format.Root.Rows\Conta do Credor(CreditorAccount)\Identificação'.
23. Na árvore, selecione 'Pagamentos = format.Root.Rows\Conta do Credor(CreditorAccount)\Identificação\IBAN'.
24. Clique em Associar.
25. Clique na guia Validações.
26. Clique em Novo.
    * Adicionar uma nova regra de validação que exibe um erro para qualquer linha no arquivo de análise que contenha um código IBAN inválido.  
27. Clique em Editar condição.
28. Na árvore, expanda 'check_codes'.
29. Na árvore, selecione 'check_codes\verifyMOD1271_36'.
30. Clique em Adicionar fonte de dados.
31. No campo Fórmula, digite 'check_codes.verifyMOD1271_36('.
    * check_codes.verifyMOD1271_36(  
32. Na árvore, expanda 'format'.
33. Na árvore, expanda 'formato\Raiz: Sequência(Root)'.
34. Na árvore, expanda 'formato\Raiz: Sequência(Root)\Linhas: Sequência 1..* (Rows)'.
35. Na árvore, expanda 'formato\Raiz: Sequência(Root)\Linhas: Sequência 1..* (Rows)\Campos: Sequência 1..1 (Fields)'.
36. Na árvore, selecione 'formato\Raiz: Sequência(Root)\Linhas: Sequência 1..* (Rows)\Campos: Sequência 1..1 (Fields)\IBAN: String(IBAN)'.
37. Clique em Adicionar fonte de dados.
38. No campo Fórmula, digite 'check_codes.verifyMOD1271_36(format.Root.Rows.Fields.IBAN)'.
    * check_codes.verifyMOD1271_36(format.Root.Rows.Fields.IBAN)  
39. Clique em Salvar.
40. Feche a página.
    * A condição de validação foi configurada para retornar FALSE para qualquer código IBAN inválido, chamando o método existente 'verifyMOD1271_36' da classe de aplicativo 'ISO7064'. Observe que o valor do código IBAN é definido dinamicamente no tempo de execução como o argumento do método de chamada baseado no conteúdo do arquivo TXT de análise.   
41. Clique em Editar mensagem.
42. No campo Fórmula, digite 'CONCATENATE("Invalid IBAN code has been found:  ", format.Root.Rows.Fields.IBAN)'.
    * CONCATENATE("Código IBAN inválido encontrado:  ", format.Root.Rows.Fields.IBAN)  
43. Clique em Salvar.
44. Feche a página.
45. Clique em Salvar.
46. Feche a página.

## <a name="run-the-format-mapping"></a>Executar o mapeamento de formato
Para fins de teste, execute o mapeamento de formato usando o arquivo SampleIncomingMessage.txt, que foi baixado anteriormente. A saída gerada inclui dados que serão importados do arquivo TXT selecionado e preenchidos no modelo de dados personalizado durante a importação real.   
1. Clique em Executar.
    * Clique em Procurar e navegue até o arquivo SampleIncomingMessage.txt, que foi baixado anteriormente.  
2. Clique em OK.
    * Examine a saída no formato XML, que representa os dados que foram importados do arquivo selecionado e transferidos para o modelo de dados. Observe que apenas 3 linhas do arquivo TXT importado foram processadas. O código IBAN na linha 4, que não é válido, foi ignorado e uma mensagem de erro é fornecida no Log de informações.  

