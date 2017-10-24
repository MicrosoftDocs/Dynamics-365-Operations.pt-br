---
title: Configurar ordens de qualidade
description: "Este procedimento mostra como habilitar um processo de gerenciamento de qualidade no estoque de entrada que será inspecionado imediatamente após o registro de entrada."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 73981313fc662094ee4f8bb15a88271e16d41193
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-quality-orders"></a>Configurar ordens de qualidade

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como habilitar um processo de gerenciamento de qualidade no estoque de entrada que será inspecionado imediatamente após o registro de entrada. O procedimento será executado tipicamente por um gerente de qualidade. O processo inclui a criação de um grupo de qualidade, para definir os itens que estejam prestes a ser provados, e um grupo de teste para agrupar os testes que devem ser executados em itens no grupo de qualidade. Você pode executar este guia na empresa de dados de demonstração da USMF.


## <a name="enable-quality-management"></a>Habilitar gerenciamento de qualidade
1. Vá para Gerenciamento de estoque > Configuração > Parâmetros de gerenciamento de depósito e estoque.
2. Clique na guia gerenciamento de qualidade.
3. Defina a opção Usar gerenciamento de qualidade como Sim.
4. Clique em Configuração de relatório.
    * Em USMF, a configuração do relatório para a gestão de qualidade já está definida. Se isso não tivesse sido feito, você adicionaria novas linhas aqui para os diferentes tipos de relatório, e selecionaria o tipo de documento a ser usado para cada relatório.  
5. Feche a página.
6. Feche a página.

## <a name="create-a-test"></a>Criar um teste
1. Vá para Gerenciamento de estoque > Configuração > Controle de qualidade > Testes.
2. Clique em Novo.
3. No campo Teste, digite um valor.
4. No campo Descrição, digite um valor.
5. No campo Tipo, selecione 'Opção'.
    * Neste exemplo, selecionaremos a "opção" que tornará possível atribuir os resultados do teste com base nos valores predefinidos.  
6. Clique em Salvar.
7. Feche a página.

## <a name="create-test-variables-to-define-the-way-test-results-are-recorded"></a>Crie variáveis de teste para definir a forma como os resultados do teste são registrados
1. Vá para Gerenciamento de estoque > Configuração > Controle de qualidade > Variáveis de testes.
2. Clique em Novo.
3. No campo Variável, digite um valor.
4. No campo Descrição, digite um valor.
5. Clique em Salvar.
6. Clique em Resultados.
7. Clique em Novo.
8. No campo Resultado, digite um valor.
9. No campo Descrição, digite um valor.
10. No campo Status de resultado, selecione 'Passar'.
11. Clique em Salvar.
12. Clique em Novo.
13. No campo Resultado, digite um valor.
14. No campo Descrição, digite um valor.
15. Clique em Salvar.
16. Feche a página.
17. Feche a página.

## <a name="set-up-item-sampling"></a>Configurar amostragem de item
1. Vá para Gerenciamento de estoque > Configuração > Controle de qualidade > Amostragem de item.
2. Clique em Novo.
3. No campo Amostragem de item, digite um valor.
4. No campo Descrição, digite um valor.
5. No campo Valor, insira um número.
    * Esse valor é relacionado à especificação da quantidade selecionada no campo adjacente.  
6. Expandir ou recolher a seção Processo.
7. Selecionar ou desmarcar a caixa de seleção Bloqueio completo.
    * Se você selecionar esta opção, a quantidade de muitos ou da linha da ordem estará bloqueada se um teste falhar. Se você não selecionar, somente os itens na ordem de qualidade estarão bloqueados.  
8. Clique em Salvar.
9. Feche a página.

## <a name="create-a-quality-group"></a>Criar um grupo de qualidade
1. Vá para Gerenciamento de estoque > Configuração > Controle de qualidade > Grupos de qualidade.
2. Clique em Novo.
3. No campo Grupo de qualidade, digite um valor.
    * Use um nome descritivo para ajudar a identificar quais o tipo de itens o grupo conterá (seus critérios de amostragem).  
4. No campo Descrição, digite um valor.
5. Clique em Salvar.
6. Clique em Adicionar itens.
7. Selecione a linha do número do item
    * Neste exemplo a filtragem será executada com base no número do item.  
8. No campo Critérios, digite um valor.
    * Por exemplo, digite T* para filtrar os números de item que começam com T.  
9. Clique em OK.
10. Clique em OK.
11. Clique em Grupos de qualidade de item.
12. Feche a página.
13. Feche a página.

## <a name="create-a-test-group"></a>Criar um grupo de teste
1. Vá para Gerenciamento de estoque > Configuração > Controle de qualidade > Grupos de teste.
2. Clique em Novo.
3. No campo Grupo de teste, digite um valor.
    * Insira ao grupo de testes um nome que ajude a lembrar que tipo de teste está sendo executado, e com qual grupo de qualidade ele deve ser associado. Por exemplo, deve ser usado com um grupo de qualidade que selecione os itens que começam com “O”, você pode chamá-lo de “Testes de item T“.  
4. No campo Descrição, digite um valor.
5. No campo de amostragem do item, selecione a linha de amostragem do item que você criou anteriormente.
6. Na lista, localize e selecione o PDV desejado.
7. Clique em Adicionar.
8. No campo de número de sequência, insira um número.
9. No campo Teste, selecione o teste criado anteriormente.
10. Na lista, localize e selecione o registro desejado.
11. Clique na guia Teste.
12. No campo Variável, selecione o teste variável criado anteriormente
13. Na lista, localize e selecione o registro desejado.
14. No campo Resultado padrão, clique no botão suspenso para abrir a pesquisa.
15. Na lista, clique no link na linha selecionada.
16. Clique em Salvar.
17. Feche a página.

## <a name="define-when-quality-orders-will-be-created"></a>Define quando as ordens de qualidade serão criadas
1. Vá para Gerenciamento de estoque > Configuração > Controle de qualidade > Associações de qualidade.
2. Clique em Novo.
3. No campo Tipo de referência, selecione uma opção.
4. No campo Código de item, selecione 'Grupo'.
    * Neste exemplo, selecionaremos o "Grupo" e usaremos o grupo de qualidade que criamos antes. Você também pode definir para "Tabela" para especificar manualmente os itens, ou selecionar "Tudo" para adicionar todos os itens na ordem de qualidade.  
5. No campo Item, selecione o grupo de qualidade criado anteriormente.
    * As opções disponíveis no campo item dependem do que você definiu no campo Código do item.  
6. Na lista, localize e selecione o PDV desejado.
7. Expandir ou recolher a seção Processo.
8. No campo Tipo de evento, selecione uma opção.
    * Este é o evento que dispara o teste. As opções disponíveis dependem de qual processo você selecionou no campo Tipo de referência.  
9. No campo Execução, selecione uma opção.
10. Expandir ou recolher a seção Processo de ordem de qualidade.
11. No campo Bloqueio de evento, clique no botão suspenso para abrir a pesquisa.
    * Este campo mostra a lista de processos que é possível bloquear se a ordem de qualidade ainda estiver aberta. As opções dependem de qual opção selecionada no campo Tipo de evento.  
12. Na lista, clique no link na linha selecionada.
    * Isso dependerá dos valores selecionados anteriormente. Selecione se os processos a seguir devem ser bloqueados durante as ordens de qualidade abertas vinculados a um documento de linha de origem.  
13. Expandir ou recolher a seção Especificações.
14. No campo Grupo de teste, selecione o grupo de teste criado anteriormente.
15. Na lista, localize e selecione o registro desejado.
16. Clique em Salvar.
17. Feche a página.

