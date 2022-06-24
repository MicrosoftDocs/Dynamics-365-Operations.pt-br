---
title: ER Configurar o formato para fazer contagem e soma (Parte 4 - Executar formato)
description: Este artigo descreve como configurar um formato de relatório eletrônico para contar e somar com base nos dados da saída de texto já gerada. (Parte 4)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, IntrastatParameters, Intrastat, InventItemIdLookupSimple, IntrastatCommodityLookup, ERFormatMappingRunLogTable, DocuView
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 665f51b3c0b7dd4fac1ca26f6918ee1e6c9fa85a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848741"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-4---run-format"></a>ER Configurar o formato para fazer contagem e soma (Parte 4 - Executar formato)

[!include [banner](../../includes/banner.md)]

As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou de desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para fazer a contagem e soma com base nos dados já gerados do texto de saída. Essas etapas podem ser executadas na empresa DEMF.

Para concluir estas etapas, primeiramente conclua as etapas no procedimento "ER Configurar o formato para contagem e soma (Parte 3: usar cálculos para obter o resultado)".

Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.


## <a name="test-this-configuration-for-generation-of-the-intrastat-reports"></a>Testar esta configuração para a geração de relatórios intrastat
1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.
2. Clique em Configurações de relatórios.
3. Na árvore, expanda 'Modelo intrastat'.
4. Na árvore, expanda 'Modelo intrastat\Intrastat (DE)'.
5. Na árvore, selecione "Modelo intrastat\Intrastat (DE)\Intrastat (DE) com contagem e soma".
6. No Painel de Ação, clique em Configurações.
7. Clique em Parâmetros de usuário.
8. Selecione Sim no campo Executar configurações.
9. Clique em OK.
10. Clique em Editar.
11. Selecione Sim no campo Executar Rascunho.
12. Clique em Salvar.
13. Acesse Imposto > Configuração > Comércio exterior > Parâmetros de comércio exterior.
14. Expanda a seção Relatório eletrônico.
15. Selecione a configuração "Intrastat (DE) com contagem e soma".
16. Selecione a configuração "Intrastat (DE) com contagem e soma".
17. Clique em Salvar.
18. Feche a página.
19. Acesse Imposto > Declarações > Comércio exterior > Intrastat.
20. Clique em Saída.
21. Clique em Relatório.
    * Execute o processo de geração de relatórios intrastat.  
22. No campo Data inicial, defina a data como '01-01-2000'.
    * Defina as datas inicial e final para o período do relatório que incluam a existente nas transações do formulário.  
23. No campo Data final, defina a data como '31-12-2022'.
    * Defina as datas inicial e final para o período do relatório que incluam a existente nas transações do formulário.  
24. No campo Direção, selecione 'Entradas'.
25. Selecione Sim no campo Gerar arquivo.
26. Clique em OK.
    * Examine as saídas criadas com as linhas de resumo no final.  
27. Clique em Novo.
28. Na lista, marque a linha selecionada.
29. No campo Direção, selecione 'Expedições'.
30. No campo Número do item, insira ou selecione um valor.
31. No campo Mercadoria, insira ou selecione um valor.
32. Defina o peso como '10'.
33. Defina o valor da fatura como '10000'.
34. Defina o valor estatístico como '10000'.
35. Clique em Saída.
36. Clique em Relatório.
37. No campo Direção, selecione 'Expedições'.
38. Clique em OK.
    * Examine as saídas criadas com as linhas de resumo no final. Observe que elas foram modificadas em comparação com a primeira execução.  

## <a name="run-this-configuration-in-debug-mode-to-review-the-collected-counting--summing-data"></a>Execute esta configuração no modo de depuração para analisar os dados de contagem e soma coletados
1. Acesse Administração da organização > Relatório eletrônico > Configurações.
2. Na árvore, expanda 'Modelo intrastat'.
3. Na árvore, expanda 'Modelo intrastat\Intrastat (DE)'.
4. Na árvore, selecione "Modelo intrastat\Intrastat (DE)\Intrastat (DE) com contagem e soma".
5. No Painel de Ação, clique em Configurações.
6. Clique em Parâmetros de usuário.
7. Selecione Sim no campo Executar em modo de depuração.
8. Clique em OK.
9. Feche a página.
10. Acesse Imposto > Declarações > Comércio exterior > Intrastat.
11. Clique em Saída.
12. Clique em Relatório.
13. Clique em OK.
14. Feche a página.
15. Acesse Administração da organização > Relatório eletrônico > Configurações.
16. Na árvore, expanda 'Modelo intrastat'.
17. Na árvore, expanda 'Modelo intrastat\Intrastat (DE)'.
18. Na árvore, selecione "Modelo intrastat\Intrastat (DE)\Intrastat (DE) com contagem e soma".
19. Clique em Logs de depuração.
    * Observe que um registro de log de depuração foi criado para o processo de execução da configuração selecionada.  
20. Clique em Anexar.
21. Clique em Abrir.
    * Examine o arquivo XML criado que contém os detalhes da contagem e soma que foram coletados durante a execução da configuração selecionada.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]