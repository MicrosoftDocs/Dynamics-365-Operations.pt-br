---
title: Recursos de grade
description: Este tópico descreve vários recursos avançados do controle de grade. O novo recurso de grade deve estar habilitado para ter acesso a esses recursos.
author: jasongre
manager: AnnBe
ms.date: 06/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 88a4e2fe69000f8034729d468ad5fd108d435c3e
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2020
ms.locfileid: "3431351"
---
# <a name="grid-capabilities"></a>Recursos de grade

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

O novo controle de grade fornece vários recursos úteis e eficientes que podem ser usados para melhorar a produtividade do usuário, construir exibições mais interessantes dos dados e obter insights significativos sobre seus dados. Este artigo abordará os seguintes recursos: 

-  Calculando totais
-  Agrupamento de dados
-  Digitação à frente do sistema
-  Avaliação de expressões matemáticas 

## <a name="calculating-totals"></a>Calculando totais
Nos aplicativos do Finance and Operations, os usuários podem ver os totais na parte inferior das colunas numéricas em grades. Esses totais são mostrados em uma seção de rodapé na parte inferior da grade. 

### <a name="showing-the-grid-footer"></a>Mostrando o rodapé da grade
Existe uma área de rodapé na parte inferior de cada grade tabular nos aplicativos do Finance and Operations. O rodapé pode mostrar informações valiosas relacionadas aos dados que aparecem na grade. Veja alguns exemplos dessas informações:

- O número de linhas selecionadas na tabela (quando mais de um registro é selecionado)
- Totais gerais na parte inferior das colunas numéricas configuradas
- O número de linhas no conjunto de dados 

Esse rodapé é ocultado por padrão, mas pode ser facilmente ativado. Para mostrar o rodapé de uma grade, clique com o botão direito do mouse em um cabeçalho de coluna na grade e selecione a opção **Mostrar rodapé**. Depois que o rodapé tiver sido ativado para uma determinada grade, essa configuração será lembrada até que o usuário opte por ocultar o rodapé, o que pode ser feito clicando com o botão direito do mouse em um cabeçalho de coluna e selecionando **Ocultar rodapé**.  Observe que o posicionamento da ação **Mostrar rodapé/Ocultar rodapé** deve ser realocado em uma atualização futura. 

### <a name="specifying-columns-with-totals"></a>Especificando colunas com totais
No momento, nenhuma coluna será configurada para mostrar os totais por padrão. Pelo contrário, essa atividade é considerada de configuração única, semelhante ao ajuste das larguras das colunas em grades. Após especificação de que deseja ver os totais de uma coluna, essa configuração será lembrada na próxima vez que você visitar a página.  

Há duas maneiras de configurar uma coluna para mostrar um total: 

- Clique com o botão direito do mouse na coluna da qual você deseja ver um total e selecione **Totalizar esta coluna**. Essa ação causa três eventos:

    1. O rodapé fica visível. 
    2. Sua preferência para ver um total dessa coluna é salva. 
    3. Um cálculo de totais é iniciado para essa coluna e quaisquer outras colunas que você configurou anteriormente para ver totais. O tempo necessário para mostrar um total depende do tamanho do conjunto de dados que você está totalizando.

- Depois que o rodapé estiver visível, selecione **Mostrar total** na área do rodapé na parte inferior da coluna da qual você deseja ver um total. Se não houver colunas configuradas, o botão **Mostrar total** estará disponível para todas as colunas numéricas. 

    Depois que houver pelo menos uma coluna configurada para totais, os botões **Mostrar total** só ficarão disponíveis com a passagem do mouse ou na focalização. A ação de selecionar **Mostrar total** só salva sua preferência para ver um total nesta coluna, a fim de que a preferência seja aplicada durante futuras visitas à página. No rodapé, esse estado é indicado por um traço que aparece na coluna. (Como alternativa, se o conjunto de dados for pequeno o suficiente, um total será mostrado imediatamente.)

Se você cometer um erro e não quiser mais ver um total em uma determinada coluna, clique com o botão direito do mouse na coluna e selecione **Ocultar total** ou selecione o botão **Ocultar total** no rodapé dessa coluna. Essa preferência também será salva para futuras visitas à página. 

### <a name="calculating-totals"></a>Calculando totais
Quando você acessa uma página com o rodapé visível e as colunas já configuradas para totais, os totais podem ou não ser mostrados no rodapé. O comportamento depende do tamanho do conjunto de dados na página. Se o conjunto de dados for suficientemente pequeno, os totais serão mostrados automaticamente, com o número de linhas no conjunto de dados. Se houver traços no rodapé sob as colunas que você configurou para os totais, significa que o conjunto de dados é muito grande para que o sistema mostre os totais imediatamente e uma ação explícita é necessária para calcular os totais. Para isso, clique no botão **Calcular**, no rodapé, ou clique com o botão direito do mouse em uma coluna para a qual deseja o total e selecione **Totalizar esta coluna**.  

Se o cálculo estiver demorando muito, você poderá cancelar a operação selecionando o botão **Cancelar**. Às vezes, no entanto, o conjunto de dados será grande demais para calcular os totais (um limite imposto pela sua organização) e você será notificado para filtrar mais os dados.

Os totais serão atualizados automaticamente à medida que você atualizar, excluir ou criar linhas no conjunto de dados.  

## <a name="grouping-data"></a>Agrupamento de dados
Geralmente, os usuários corporativos precisam executar análises ad hoc de dados. Embora isso possa ser feito por meio da exportação de dados do Microsoft Excel e usando tabelas dinâmicas, o recurso **Agrupamento** nas grades tabulares permite que os usuários organizem seus dados de modos atrativos em seus aplicativos do Finance and Operations. Como esse recurso estende o recurso **Totais** , o **Agrupamento** também permite obter insights significativos sobre os dados fornecendo subtotais no nível de grupo.

Para usar esse recurso, clique com o botão direito do mouse na coluna pela qual deseja agrupar e selecione **Agrupar por esta coluna**. Essa ação vai classificar os dados pela coluna selecionada, adicionar uma nova coluna Agrupar por ao início da grade e inserir "linhas do cabeçalho" no início de cada grupo. Essas linhas de cabeçalho fornecem as seguintes informações sobre cada grupo: 
-  Valor de dados para o grupo 
-  Etiqueta da coluna (Essas informações serão especialmente úteis depois que vários níveis de agrupamento forem compatíveis.)
-  Número de linhas de dados neste grupo
-  Subtotais de qualquer coluna configurada para mostrar totais

Com [Exibições salvas](saved-views.md) habilitadas, esse agrupamento pode ser salvo por personalização como parte de uma exibição para acesso rápido na próxima vez que você visitar a página.  

Se você selecionar **Agrupar por esta coluna** em uma coluna diferente, o agrupamento original será substituído, pois só há suporte para um nível de agrupamento na versão 10.0.9 com atualização 33 da plataforma.

Para desfazer o agrupamento em uma grade, clique com o botão direito do mouse na coluna de agrupamento e selecione **Desagrupar**.  

## <a name="typing-ahead-of-the-system"></a>Digitação à frente do sistema
Em vários cenários comerciais, a capacidade de inserir rapidamente dados no sistema é muito importante. Antes que o novo controle de grade tenha sido introduzido, os usuários podem alterar os dados somente na linha atual. Antes de criar uma nova linha ou alternar para uma linha diferente, eles foram forçados a esperar o sistema validar com êxito as alterações. Para reduzir o tempo durante o qual os usuários esperam que as validações sejam concluídas e para melhorar a produtividade do usuário, a nova grade ajusta essas validações para que sejam assíncronas. Portanto, o usuário pode ir para outras linhas para fazer alterações enquanto as validações de linhas anteriores estão pendentes. 

Para dar suporte a esse novo comportamento, uma nova coluna para o status da linha foi adicionada à direita da coluna de seleção de linha quando a grade está no modo de edição. Esta coluna indica um dos seguintes status:

- **Em branco** – Nenhuma imagem de status indica que a linha foi salva com êxito pelo sistema.
- **Processamento pendente** – Este status indica que as alterações na linha ainda não foram salvas pelo servidor, mas que estão em uma fila de alterações que devem ser processadas. Antes de executar a ação fora da grade, você deve aguardar até que todas as alterações pendentes sejam processadas. Além disso, o texto nessas linhas fica em itálico para indicar o status não salvo das linhas. 
- **Estado inválido** – esse status indica que algum aviso ou mensagem foi disparado durante o processamento da linha e pode ter impedido o sistema de salvar as alterações nessa linha. Na grade antiga, se a operação de salvamento não teve êxito, você foi forçado a voltar para a linha para corrigir o problema imediatamente. No entanto, na nova grade, você é notificado de que um problema de validação foi encontrado, mas pode decidir quando deseja corrigir os problemas na linha. Quando estiver pronto para corrigir um problema, você poderá mover o foco manualmente de volta para a linha. Alternativamente, você pode selecionar a ação **Corrigir este problema**. Esta ação move imediatamente o foco para a linha que tem o problema e permite que você faça edições dentro ou fora da grade. Observe que o processamento de linhas pendentes subsequentes é interrompido até que este aviso de validação seja resolvido. 
- **Em pausa** – Esse status indica que o processamento pelo servidor está pausado porque a validação da linha disparou uma caixa de diálogo pop-up que requer entrada do usuário. Como o usuário pode estar inserindo dados em alguma outra linha, a caixa de diálogo pop-up não é imediatamente apresentada ao usuário. Em vez disso, ele será apresentado quando o usuário optar por retomar o processamento. Esse status é acompanhado por uma notificação que informa o usuário sobre a situação. A notificação inclui uma ação **Retomar o processamento** que irá disparar a caixa de diálogo pop-up.  
    
Quando os usuários inserem dados antes do local em que o servidor está processando, eles podem esperar algumas degradações na experiência de entrada de dados, como a falta de pesquisas, a validação no nível de controle e a entrada de valores padrão. Recomenda-se que os usuários que precisam de uma lista suspensa para localizar um valor aguardem até que o servidor volte para a linha atual. A validação do nível de controle e a entrada de valores padrão também ocorrerão quando o servidor processar essa linha.   

### <a name="pasting-from-excel"></a>Colando a partir do Excel
Os usuários sempre foram capazes de exportar dados de grades em aplicativos do Finance and Operations para o Excel usando o mecanismo de **Exportação para o Excel**. No entanto, a capacidade de inserir dados antes do sistema permite que a nova grade dê suporte à cópia de tabelas do Excel e colando-as diretamente em grades em aplicativos do Finance and Operations. A célula de grade na qual a operação de colagem é iniciada determina onde a tabela copiada começa a ser colada. O conteúdo da grade é substituído pelo conteúdo da tabela copiada, exceto em dois casos:

- Se o número de colunas na tabela copiada exceder o número de colunas que permanecem na grade, iniciando a partir do local de colagem, o usuário será notificado de que as colunas extras foram ignoradas. 
- Se o número de linhas na tabela copiada exceder o número de linhas na grade, a partir do local de colagem, as células existentes serão sobrescritas pelo conteúdo colado e todas as linhas extras da tabela copiadas serão inseridas como novas linhas na parte inferior da grade. 

## <a name="evaluating-math-expressions"></a>Avaliação de expressões matemáticas
Como um acelerador de produtividade, os usuários podem inserir fórmulas matemáticas em células numéricas em uma grade. Eles não precisam fazer o cálculo em um aplicativo fora do sistema. Por exemplo, se você digitar **=15\*4** e pressionar a tecla **Tab** para sair do campo, o sistema avaliará a expressão e salvará um valor de **60** para o campo.

Para que o sistema reconheça um valor como uma expressão, inicie o valor com um sinal de igualdade (**=**). Para obter mais informações sobre os operadores e a sintaxe permitidos, consulte [Símbolos matemáticos permitidos](http://bugwheels94.github.io/math-expression-evaluator/#supported-maths-symbols).

## <a name="frequently-asked-questions"></a>Perguntas frequentes
### <a name="how-do-i-enable-the-new-grid-control-in-my-environment"></a>Como habilitar o novo controle de grade no meu ambiente? 

**10.0.9 / Atualização de plataforma 33 e mais recente** O recurso **Novo controle de grade** está disponível diretamente no Gerenciamento de recursos em todos os ambientes. Assim como outros recursos de versão prévia pública, a ativação deste recurso na produção está sujeita ao [Contrato de Termos de Uso Complementares](https://go.microsoft.com/fwlink/?linkid=2105274).  

**10.0.8 / Atualização de plataforma 32 e 10.0.7 / Atualização da plataforma 31** O recurso **Novo controle de grade** pode ser habilitado nos ambientes da Camada 1 (Desenvolvimento/Teste) e da Camada 2 (Área Restrita) a fim de fornecer testes adicionais e alterações de design seguindo as etapas abaixo.

1.  **Habilitar a versão de pré-lançamento**: execute esta instrução SQL: 

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, enabled, FLIGHTSERVICEID, PARTITION) VALUES('CLIReactGridEnableFeature', 1, 0, 5637144576);`

2. **Redefinir o IIS** para liberar o cachê de liberação estático. 

3.  **Localizar o recurso**: navegue até o espaço de trabalho **Gerenciamento de recursos**. Se **Novo controle de grade** não aparecer na lista de todos os recursos, selecione **Verificar por atualizações**.   

4.  **Habilitar o recurso**: localize o recurso **Novo controle de grade** na lista de recursos e selecione **Habilitar agora** no painel de detalhes. Observe que uma atualização do navegador é necessária. 

Todas as sessões de usuário subsequentes começarão com o novo controle de grade habilitado.

## <a name="known-issues"></a>Problemas conhecidos
Esta seção mantém uma lista de problemas conhecidos do novo controle de grade enquanto o recurso está em um estado de visualização.  

### <a name="open-issues"></a>Questões em aberto

- As listas de cartões que foram processadas como várias colunas agora são processadas como uma única coluna.
- As listas agrupadas não são processadas como grupos ou em colunas separadas.

### <a name="fixed-as-part-of-10013"></a>Corrigido como parte do 10.0.13

> [!NOTE]
> As informações a seguir estão sendo fornecidas para que você possa planejar de acordo. Para obter mais informações sobre a agenda de lançamentos de destino da versão 10.0.13, consulte [Disponibilidade das atualizações do serviço](../../fin-ops/get-started/public-preview-releases.md).

- [KB 4563317] As dicas de ferramentas não são mostradas para imagens.

### <a name="fixed-as-part-of-10012"></a>Corrigido como parte do 10.0.12

- [KB 4558545] Os controles de tabela não atualizam o conteúdo dos itens exibidos.
- [KB 4558570] Os itens ainda são mostrados na página após a exclusão do registro.
- [KB 4558572] Estilo associado à extensão estendida do painel de listagem **ExtendedStyle** não é aplicado.
- [KB 4558573] Os erros de validação não podem ser corrigidos quando a alteração necessária está fora da grade.
- [KB 4558584] Os números negativos não são renderizados corretamente.
- [KB 4560726] Um "erro de cliente inesperado" ocorre após a troca entre listas usando um controle de modo de exibição de lista.
- [KB 4562141] Os índices de grade são desativados após um novo registro ser adicionado.
- [KB 4562151] As opções de gravador de tarefas **Validar** e **Copiar** não estão disponíveis para controles de data/número. 
- [KB 4562153] As caixas de seleção com várias seleções não ficam visíveis em grades da lista/placa.
- [KB 4562646] Às vezes, você não pode clicar fora da grade após selecionar várias linhas na grade.
- [KB 4562647] O foco é redefinido para o primeiro controle na caixa de diálogo **Publicar** após uma nova linha ser adicionada na grade de funções de segurança.
- [KB 4563310] A visualização avançada não é fechada após a alteração de uma linha.
- [KB 4563313] Um "erro de cliente inesperado" ocorre no Internet Explorer quando um valor é selecionado em uma pesquisa.
- [KB 4563324] A navegação não funciona após a abertura do espaço de trabalho **Gerenciamento de pessoal**.

### <a name="fixed-as-part-of-10011"></a>Corrigido como parte do 10.0.11

- [Questão 432458] Linhas vazias ou duplicadas são mostradas no início de algumas coleções filhas.
- [KB 4549711] As linhas em uma proposta de pagamento não podem ser removidas corretamente após a habilitação do novo controle de grade.
- [KB 4558374] Os registros que exigem uma caixa de diálogo de seletor polimórfico não podem ser criados.
- [KB 4558375] O texto de ajuda não é exibido em colunas na nova grade.
- [KB 4558376] As grades do painel de lista não são processadas na altura correta em Internet Explorer.
- [KB 4558377] As colunas da caixa de combinação que têm largura de **SizeToAvailable** não são processadas em algumas páginas.
- [KB 4558378] A busca detalhada às vezes abre o registro errado.
- [KB 4558379] Ocorre um erro quando as pesquisas são abertas onde **ReplaceOnLookup**=**Não**.
- [KB 4558380] O espaço disponível na grade não é preenchido imediatamente depois que parte da página é recolhida.
- [KB 4558381] Os números negativos não são renderizados corretamente/os usuários podem ficar presos depois que problemas de validação são encontrados.
- [KB 4558382] Ocorreram erros inesperados do cliente.
- [KB 4558383] Controles fora da grade não são atualizados após o último registro ser excluído.
- [KB 4558587] Os grupos de referência que possuem caixas de combinação para campos de substituição não mostram valores.
- [KB 4562143] Os campos não são atualizados depois que um processamento de alteração/grade de linha fica preso após a exclusão da linha.
- [KB 4562645] Uma exceção ocorre quando uma pesquisa é aberta enquanto os testes de ferramentas de administração de servidor remoto (RSAT) estão em execução.

### <a name="fixed-as-part-of-10010"></a>Corrigido como parte do 10.0.10

- [Questão 414301] Alguns dados das linhas anteriores desaparecem quando novas linhas são criadas.
- [Bug 417044] Não há mensagens de grade vazias para grades de estilo de lista.
- [KB 4539058] Algumas grades (geralmente nas Guias Rápidas) não são renderizadas (mas serão processadas se você sair do zoom).
- [KB 4549734] As linhas ativas não serão tratadas como marcadas se a coluna de marcação estiver oculta.
- [KB 4549796] Os valores não podem ser editados em uma grade quando ela está em modo de exibição.
- [KB 4558367] A seleção de texto fica inconsistente quando as linhas são alteradas.
- [KB 4558368] Várias seleções via teclado são permitidas em cenários de seleção única.
- [KB 4558369] As imagens de status desaparecem na grade hierárquica.
- [KB 4558370] Uma nova linha não é exibida com rolagem na exibição.
- [KB 4558372] A nova grade ficará presa no modo de processamento se o número de colunas no conteúdo colado exceder o número de colunas restantes na grade.
- [KB 4562631] Os valores de tempo não estão formatados corretamente.

### <a name="quality-update-for-1009platform-update-33"></a>Atualização de qualidade para 10.0.9/Atualização da plataforma 33

- [KB 4550367] Os valores de tempo não estão formatados corretamente.
