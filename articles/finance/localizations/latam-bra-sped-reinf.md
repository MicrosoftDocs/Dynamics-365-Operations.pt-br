---
title: Eventos SPED-Reinf
description: Este tópico explica como configurar eventos SPED-Reinf usando Livros fiscais e a estrutura de registro de relatórios SII.
author: sndray
ms.date: 05/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: cb1e0a4305ed04c1d2483f24cb93bc00e1b880d39dfe244ad9f0e7f9fc57a1ca
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6765005"
---
# <a name="sped-reinf-events"></a>Eventos SPED-Reinf

[!include [banner](../includes/banner.md)]

Todas as informações que o SPED-Reinf fornece sobre impostos e contribuições em um determinado período de apuração são conhecidas como uma *movimentação*. Portanto, cada movimentação pode conter um ou mais eventos.

Para fechar a transmissão de eventos periódicos para um movimento determinado em um período de avaliação específico, é necessário enviar o evento R-2099, *Fechamento do evento periódico*. Depois que o evento de fechamento é processado e validado, ele é aceito. A aceitação do evento de fechamento finaliza a soma das bases de cálculo incluídas na movimentação. O crédito de imposto poderá então ser calculado e o DARF poderá ser gerado para coletar os impostos e as contribuições devidos.

Caso seja necessário enviar uma correção ou novos eventos para um movimento que já está fechado, é necessário reabrir o movimento enviando o evento R-2098, *Reabertura do evento periódico*. Depois que o movimento for reaberto, envie um novo evento de fechamento.

**Quando não há movimentações no período de apuração**

A situação “sem movimentação” para um contribuinte ocorre somente quando não há informações a serem enviadas ao grupo de eventos periódicos do evento R-2010 ao evento R-2070. Neste caso, o evento R-2099, *Fechamento do evento periódico*, que fornece as informações para fechamento, declara a não ocorrência de transações no primeiro período de avaliação do ano em que essa situação ocorre. Se a situação “sem movimentação” persistir nos anos seguintes, o contribuinte deverá repetir esse procedimento no mês de janeiro de cada ano.

**Protocolo de recebimento**

O protocolo de recebimento confirma que as informações enviadas foram validadas e entregues com êxito ao ambiente do SPED-Reinf. O protocolo de recebimento é o ponto inicial para corrigir ou excluir um determinado evento, se a correção e a exclusão forem permitidas.

Cada evento transmitido tem um protocolo de recebimento. Para corrigir um evento, insira o número do protocolo de recebimento do evento.

A quantidade de tempo que os protocolos de recebimento são mantidos no banco de dados do governo não é definida. Portanto, como precaução, é importante que o contribuinte retenha os protocolos, pois eles são prova de que a obrigação fiscal auxiliar foi cumprida.

> [!NOTE]
> O protocolo de entrega consiste em informações transitórias que comprovam que o evento foi transmitido e que a validação apropriada será processada. O protocolo não demonstra conformidade com a obrigação auxiliar.

**Aditamento e correção**

O procedimento para corrigir informações enviadas ao SPED-Reinf ocorre somente nos eventos R-1000, *Informações do contribuinte* e R-1070, *Tabela administrativa e de ações judiciais*.

Em todos os outros casos em que as informações enviadas devem ser corrigidas, o procedimento para a correção ou exclusão deve ser usado.

**Eventos de exclusão**

Para excluir eventos que foram aprovados pela autoridade fiscal, mas fornecidas incorretamente, é necessário enviar o evento R-9000, *Evento de exclusão*. Nesse evento, é necessário identificar o evento a ser excluído preenchendo a marca **Tipo de evento** (**TpEvento**). Você também deve preencher o **Número de recebimento do evento** (**NRRECEVT**), que especifica o número do protocolo de recebimento do arquivo que foi enviado e deve ser excluído.

**Assinatura digital**

O certificado digital usado no SPED-Reinf deve ser emitido por uma autoridade de certificação credenciada pela ICP-Brasil. Certificados podem pertencer a duas séries: **A** e **S**. 

- **A** – Esta série inclui os certificados de assinatura digital que são usados para confirmação de identidade na Web em emails, redes privadas virtuais (VPNs) e documentos eletrônicos, com verificação da integridade de suas informações.
- **S** – Esta série inclui os certificados de confidencialidade que são usados na codificação de documentos, bancos de dados, mensagens e outras informações eletrônicas confidenciais.

O certificado digital deve ser do tipo **A1** ou **A3**. Os certificados digitais **A1** são armazenados no computador em que são usados. Os certificados digitais **A3** são armazenados em um dispositivo portátil com resistência a violações que contém um chip que pode realizar assinaturas digitais. Esses dispositivos incluem cartões inteligentes e tokens. Como toda operação é feita pelo chip no dispositivo e não existe acesso externo à chave privada do certificado digital, esses dispositivos são razoavelmente seguros.

Os certificados digitais são obrigatórios em duas situações:

- **Para ações de fornecimento:** antes de a solicitação de fornecimento para o SPED-Reinf ser iniciada, o certificado digital do solicitante é usado para ajudar a garantir a segurança do tráfego de informações na internet. Para que o certificado digital seja aceito como uma função de transmissor, ele deve ser do tipo e-CNPJ.
- **Para assinatura de documentos:** eventos podem ser gerados por qualquer estabelecimento fiscal da entidade legal ou de seu proxy. No entanto, o assinante digital desses eventos deve pertencer ao estabelecimento fiscal principal (matriz), seu representante legal ou um advogado concedido por meio de proxy eletrônico e não eletrônico.

Os certificados digitais que são usados para assinar os eventos que são enviados ao SPED-Reinf devem ser habilitados para a função de assinatura digital de acordo com a política do certificado.

Os eventos no SPED-Reinf devem ser transmitidos usando um certificado digital válido. No entanto, uma exceção será feita para micro e pequenas empresas (ME e EPP) que atendam aos critérios do Simples Nacional e possuam sete funcionários ou menos. Essa empresas podem transmitir seus eventos usando um código de acesso.

## <a name="general-process"></a>Processo geral 

O processo para gerar cada evento inclui as seguintes etapas.

1. Use uma mensagem eletrônica para criar, validar e entregar o evento ou lote de eventos por meio de itens de mensagem eletrônica.
2. O serviço Web da autoridade fiscal recebe o lote e valida seu conteúdo.
3. O serviço Web retorna o resultado do processamento. Se os eventos ou o lote de eventos forem recebidos com êxito, um protocolo de recebimento será retornado. Caso contrário, uma mensagem de erro será exibida. Nesse caso, o contribuinte pode corrigir os erros e reenviar o evento por meio de um novo lote.

![Processo geral.](media/bra-general-process.png)

Os eventos são transmitidos às autoridades fiscais usando a funcionalidade Mensagem eletrônica. Essa funcionalidade estabelece um relacionamento bilateral, automatizado e instantâneo entre os serviços da Web e o contribuinte.

As ilustrações a seguir mostram as ações que são realizadas e o status de itens de mensagem que fazem com que cada evento seja aprovado ou rejeitado ao ser fornecido pela primeira vez (Inserção), atualizado (Correção/Atualização) e cancelado ou excluído (Cancelamento/Exclusão).

![Ações de fluxo.](media/bra-flow-actions.png)

### <a name="actions"></a>Ações

**Inserção**

Este fluxo é usado para entregar qualquer evento pela primeira vez.

![Inserção.](media/bra-insertion-flow.png)

**Aditamento/Atualização**

![Atualizar.](media/bra-amendment-update-flow.png)

**Cancelamento/Exclusão**

![Cancelar.](media/bra-cancel-delete-flow.png)

**Consultar evento 5011 (do evento R-2099)**

![Evento de consulta 5011.](media/bra-inquire-event-5011.png)

## <a name="booking-period"></a>Período de escrituração

Antes de você começar a gerar esses eventos, reserve todos os documentos fiscais no evento relacionado. 

1. Acesse **Livros fiscais** \> **Comum** \> **Período da reserva** e selecione o período de reserva e estabelecimento fiscal (cabeçalho).
2. Selecione **Sincronizar** para sincronizar todos os documentos fiscais. 
3. Na seção **SPED REINF**, selecione o evento relacionado:

    - Selecione **R-2010** e selecione **Atualizar** para coletar todos os documentos fiscais recebidos em que o modelo é **SE** e o tipo de imposto é **INSS**.
    - Selecione **R-2020** e selecione **Atualizar** para coletar todos os documentos fiscais enviados em que o modelo é **SE** e o tipo de imposto é **INSS**.
    - Selecione **R-2055** e selecione **Atualizar** para coletar todos os documentos fiscais recebidos e enviados em que tenham os impostos SENAR ou GILRAT.

4. Selecione **Consultar** para visualizar os documentos fiscais que são incluídos no evento relacionado.
5. Acesse **Imposto** \> **Consultas e relatórios** \> **Mensagens eletrônicas** \> **Itens de mensagem eletrônica**, pois essa ação gerencia e controla o status dos eventos.

> [!NOTE]
> Você pode usar o filtro para incluir critérios adicionais durante a coleta de transações.
> 
> Os outros eventos que não foram detalhados antes são automaticamente gerados nos itens de mensagem eletrônica mediante condições específicas.

## <a name="event-r-1000--taxpayer-information"></a>Evento R-1000 – Informações do contribuinte

O evento R-1000 é usado para fornecer informações sobre a empresa. Esse evento deve ser entregue apenas uma vez para registrar as informações no site do governo. No entanto, após o registro inicial das informações, o evento pode ser fornecido quantas vezes for necessário para ações de manutenção, como atualizações e exclusões de dados.

Sempre que for necessário alterar qualquer atributo do contribuinte ou a data válida das informações fornecidas antes o evento R-1000 deve ser fornecido novamente. Quando o evento for refornecido, o grupo correto de marcas para a ação desejada deverá ser especificado.

Como as comunicações podem falhar devido a problemas técnicos, como tempo limite ou falhas de Internet, o contador tributário deve ser capaz de renviar o evento. Além disso, como a validação do arquivo pelo serviço Web pode falhar, o contador tributário deve ser capaz de visualizar os detalhes e corrigir os erros relacionados. Após a validação do arquivo, o protocolo de recebimento que é retornado pelo serviço Web deve ser salvo. O contador do imposto deve ser capaz de visualizar os detalhes do protocolos de recebimento, como o número e o carimbo de hora.

### <a name="repro-step--insertion"></a><a id='repro-insert'></a>Etapa de reprodução – Inserção

1. Acesse **Imposto** \> **Consultas e relatórios** \> **Mensagens eletrônicas** \> **Itens de mensagem eletrônica**.
2. No Painel de Ações, selecione **Executar processamento** e, na caixa de diálogo **Executar processamento**, no campo **Processamento**, selecione **SPED Reinf**.
3. Defina a opção **Escolher ação** como **Sim** e, em seguida, no campo **Ação**, selecione **Incluir**.

    ![Executar processamento.](media/bra-run-processing.png)

4. Selecione **OK** para confirmar as configurações.

    Um item de mensagem do tipo **Informações do contribuinte** é criado e seu status é definido como **Anexado**.

    ![Inserção de itens de mensagem eletrônica.](media/bra-electronic-message-items-insertion.png)

5. Selecione **Executar processamento** novamente e, na caixa de diálogo, no campo **Processamento**, selecione **SPED Reinf**.
6. Defina a opção **Escolher ação** como **Sim** e, em seguida, no campo **Ação**, selecione **Parâmetros adicionais** para atualizar as informações relacionadas nos campos adicionais.

    ![Parâmetros adicionais de Execução de processamento.](media/bra-run-processing-additional-parameters.png)

    ![Itens de preparação.](media/bra-preparation-items.png)

7. Selecione **OK** para confirmar as configurações. O item de mensagem do tipo **Informações do contribuinte** é atualizado, e o status do item de mensagem é alterado para **Preparado**.

    ![Status de itens de mensagem eletrônica.](media/bra-electronic-message-items-status.png)

8. Selecione **Executar processamento** novamente e, na caixa de diálogo, no campo **Processamento**, selecione **SPED Reinf**.
9. Defina a opção **Escolher ação** como **Sim** e, em seguida, no campo **Ação**, selecione **Gerar** para gerar o XML.
10. Selecione **OK** para confirmar as configurações. A caixa de diálogo **Gerar relatórios** aparece automaticamente. Na FastTab **Registros a serem incluídos**, nas opções de filtro, a ID do tipo de item de mensagem que está solicitando a geração de um arquivo XML é selecionada no campo **Item de mensagem**.

    ![Gerar relatórios.](media/bra-generate-reports.png)

11. Selecione **OK** para confirmar as configurações. O item de mensagem do tipo **Informações do contribuinte** é atualizado e seu status é alterado para **Gerado**.
12. Repita essas etapas até concluir todas as ações do fluxo Inserção.

### <a name="repro-step--amendment"></a>Etapa de reprodução – Aditamento 

No caso de alteração de qualquer dado de organização fiscal, ou caso o evento deva ser excluído por algum motivo, o evento R-1010 deve ser transmitido novamente, mas o status deve ser diferente.

Use o processo descrito na seção [Etapa Repro – Inserção](#repro-insert) e conclua todas as ações no fluxo Correção/Atualização.

Qualquer diferença entre as informações do último evento e as informações atuais será detectada.

> [!NOTE]
> Se as alterações não afetarem o evento R-1010 relacionado, você receberá a seguinte mensagem: “0 registros foram adicionados”.

#### <a name="repro-step--cancel"></a>Etapa de reprodução – Cancelamento

Se, por qualquer motivo, o contribuinte quiser cancelar ou excluir um evento que foi aceito, selecione **Cancelar** e confirme a operação. O status do evento será atualizado para **Excluído**. Conclua todas as ações no fluxo Cancelamento/Exclusão.

## <a name="event-r-1070--administrative-and-judicial-process"></a>Evento R-1070 - Processo administrativo e judicial

O evento R-1070 é usado para relatar informações sobre o processo administrativo e de ações legais à autoridade fiscal.

O processo administrativo e de ações legais pode ser iniciado pelo contribuinte ou funcionário quando os valores do seguro social forem disputados. Os procedimentos (judiciais ou administrativos) são realizados pelo tribunal. Após o juiz chegar à decisão final, ele poderá suspender os valores que foram retidos.

A finalidade desse evento é comunicar a existência de procedimentos desse tipo ao banco de dados do SPED-Reinf. Depois que os procedimentos recebem a decisão final do tribunal que suspende a elegibilidade da retenção de valores, o evento se refere a essa decisão para explicar por que os valores foram relatados como suspensos nos eventos periódicos.

Além das informações típicas que identificam o contribuinte e o evento, o evento R-1070 contém os seguintes grupos:

- Identificador do processo ou dos procedimentos
- Informações da suspensão
- Informações complementares sobre os procedimentos

Para que o evento R-1070 possa ser fornecido, crie o processo relacionado e inclua todas as informações relacionadas.

### <a name="repro-step--create-process"></a>Etapa de reprodução – Criar processo

1. Acesse **Livros fiscais** \> **Periódico** \> **SPED Reinf** \> **Processo administrativo e judicial**.

    ![Processo judicial administrativo.](media/bra-administrative-judicial-process.png)

2. Selecione **Novo** e defina os campos a seguir.

    | Campo                        | descrição |
    |------------------------------|-------------|
    | Número do processo        | Insira o número do processo atribuído pelas autoridades competentes. O sistema da autoridade fiscal valida o formato, pois há uma regra específica a ser considerada. |
    | Autor do processo            | Selecione a origem do processo. |
    | Tipo de processo              | Selecione o tipo de processo:<ul><li>Contribuinte</li><li>Outros terceiros</li><li>Administrativo</li><li>Judicial</li></ul> |
    | Cidade da seção judicial | Selecione a cidade relacionada onde o processo foi originado. |
    | Código da vara judicial | Insira o código da vara judicial. |

3. Na seção **Detalhes**, insira os detalhes dos documentos fiscais que são registrados no Finance e afetados pelo processo registrado, pois alguns deles podem ter exceções na retenção de impostos. Você pode adicionar documentos fiscais ou remover documentos fiscais adicionados.

    | Campo                            | descrição                                                                                               |
    |----------------------------------|-----------------------------------------------------------------------------------------------------------|
    | Demonstrativo                        | O identificador exclusivo da relação entre o número do processo e a nota fiscal.                 |
    | Código                             | Selecione o código de suspensão da explicação.                                                                   |
    | Tipo de serviço                     | Selecione o tipo de serviço relacionado que é aplicável à nota fiscal.                               |
    | Nota fiscal                  | Selecione a nota fiscal.                                                                               |
    | Data da decisão                 | A data da decisão, da sentença ou do despacho administrativo.                                           |
    | Valor da retenção            | O valor da retenção que foi suspenso devido a um processo legal ou administrativo.            |
    | Valor da retenção adicional | O valor adicional da retenção que foi suspenso devido a um processo legal ou administrativo. |

    > [!NOTE]
    > Siga as etapas descritas para o evento R-1000 a fim de inserir, atualizar ou cancelar o evento relacionado.

## <a name="event-r-2010--acquired-services"></a>Evento R-2010 - Serviços adquiridos

O evento periódico R-2010 é usado para relatar, ao sistema da autoridade fiscal, as informações sobre os valores de retenção para a previdência social que estão presentes em notas fiscais de serviço recebidas pelo estabelecimento fiscal. O único propósito deste evento é relatar esses documentos fiscais ao governo.

Esse evento deve ser enviado até o décimo quinto dia do mês seguinte. Por ser um evento periódico, não é recomendável enviá-lo apenas uma vez, próximo à data de vencimento. Em vez disso, envie o evento regular e frequentemente durante o período.

Além disso, a geração desse evento requer a adoção de novas semânticas para o tratamento de eventos em livros fiscais. As novas semânticas são desacopladas de uma apuração de imposto, mas ainda estão no contexto do período de escrituração. Depois que todas as notas fiscais no módulo **Livros fiscais** estiverem no contexto de um período de escrituração, o evento R-2010 também deverá ser gerado por período de escrituração.

Somente o imposto INSS Retido e o imposto sobre serviços devem ser selecionados para gerar esse evento no período de escrituração.

**Principais critérios**

- As notas fiscais são registradas e sincronizadas no estabelecimento fiscal e no período relacionado.
- As notas fiscais têm o status de **Aprovada** ou **Cancelada**.
- O modelo da nota fiscal é **SE**.
- O tipo de imposto é **INSS** e é retido (ou seja, a caixa de seleção **Imposto retido/a recuperar** é marcada).

    ![Impostos brasileiros.](media/bra-brazilian-taxes.png)

> [!NOTE]
> Nunca use o tipo de imposto **INSS-CPRB**.

O relatório é agrupado pelo valor **Tipo de código de serviço** (tabela 06 na documentação SPED-Reinf). No entanto, você deve modificar a postagem dos documentos fiscais de serviço para habilitar a captura dessas informações. Caso contrário, não é possível gerar o evento.

O evento envia quatro tipos de valores para o banco de dados do governo:

- **Retenção** – O tipo de imposto INSS Retido calculado que está vinculado à linha da nota fiscal.
- **Retenção adicional** – Uma variação do tipo de imposto INSS que está vinculado à linha da nota fiscal.
- **Retenção suspensa** – O valor do tipo de imposto INSS Retido suspenso.
- **Retenção adicional suspensa** – O valor suspenso da variação do tipo de imposto INSS que está vinculado à linha da nota fiscal.

Quando uma suspensão de valores ocorrer, o processo administrativo ou de ações legais associado deve ser especificado no evento para corroborar ou explicar os motivos da suspensão. Insira essa informação manualmente nos campos **Valor de retenção** e **Valor adicional de retenção** na página **Processo administrativo e judicial** que foi descrita neste tópico.

O evento R-2010 usa o conceito de fechamento. Depois que esse evento for fechado, o serviço Web recusará quaisquer novas entradas ou modificações nele, a menos que seja reaberto manualmente.

> [!NOTE]
> Siga as etapas descritas para o evento R-1000 a fim de inserir, atualizar ou cancelar o evento relacionado.

## <a name="event-r-2020--provided-services"></a>Evento R-2020 - Serviços fornecidos

O evento periódico R-2020 é usado para relatar, ao sistema da autoridade fiscal, as informações sobre os valores de retenção para a previdência social que estão presentes em notas fiscais de serviço emitidas pelos estabelecimentos fiscais de uma organização fiscal.

Esse evento funciona como o evento R-2010, mas você deve considerar as contas de cliente e o modelo de nota fiscal SE (saída) que é emitido pelo estabelecimento fiscal.

> [!NOTE]
> Siga as etapas descritas para o evento R-1000 a fim de inserir, atualizar ou cancelar o evento relacionado.

## <a name="event-r-2055--acquisition-from-agriculture-vendor"></a>Evento R-2055 – Aquisição de fornecedor agrário

O evento periódico R-2055 é usado para relatar ao sistema da autoridade fiscal informações sobre os valores de retenção sobre seguro social, SENAR e GILRAT que constam nos documentos fiscais recebidos pelo estabelecimento fiscal em relação aos produtos agrários. O único propósito deste evento é relatar esses documentos fiscais ao governo.

Esse evento deve ser enviado até o décimo quinto dia do mês seguinte. Por ser um evento periódico, não é recomendável enviá-lo apenas uma vez, próximo à data de vencimento. Em vez disso, envie o evento regular e frequentemente durante o período.

A geração deste evento requer a adoção da nova semântica para tratamento de eventos em livros fiscais. As novas semânticas são desacopladas de uma apuração de imposto, mas ainda estão no contexto do período de escrituração. Quando todos os documentos fiscais no módulo **Livros fiscais** estiver no contexto de um período de reserva, o evento R-2055 também deve ser gerado pelo período de reserva em **Livros fiscais** \> **Período de reserva** \> **SPED Reinf** \> **R-2055**.

**Principais critérios**

- As notas fiscais são registradas e sincronizadas no estabelecimento fiscal e no período relacionado.
- As notas fiscais têm o status de **Aprovada** ou **Cancelada**.
- O modelo de documento fiscal é **04** ou **55** (um número de série entre 920 e 969). 
- O tipo de imposto é **INSS** e é retido (ou seja, a caixa de seleção **Imposto retido/a recuperar** é marcada).
- O tipo de imposto é **Outro**, é retido (ou seja, a caixa de seleção **Imposto retido/a recuperar** é marcada), e os impostos GILRAT ou SENAR são identificados.

## <a name="event-r-2060--inss-cprb"></a>Evento R-2060 – INSS CPRB

O evento periódico R-2060 é usado para enviar informações sobre a apuração de imposto da retenção para a previdência social ao SPED-Reinf quando a organização fiscal escolher calcular a previdência social com base na receita bruta em vez da folha de pagamento.

Antes de gerar o evento, faça a avaliação de imposto por organização fiscal no módulo **Livros fiscais**. Quando esta opção é estabelecida nos parâmetros SPED-Reinf, você pode criar a avaliação de imposto para INSS-CPRB, e as taxas são calculadas automaticamente baseadas nos critérios que são definidos nos parâmetros de Livros fiscais.

O Finance obterá todos os documentos fiscais que são registrados no período relacionado e represente receita e aplicará a taxa de imposto ao valor base. A alíquota de imposto aplicada pode variar, dependendo do produto ou serviço que gerou a receita. O resultado será o valor de CPRB.

Para este propósito, um novo tipo de imposto brasileiro é criado; o **INSS-CPRB**. Este tipo de imposto é usado somente para gerar a avaliação de imposto INSS-CPRB.

> [!NOTE]
> Não use o tipo de imposto **INSS-CPRB** para outras finalidades.

Como a apuração do imposto INSS-CPRB é um tipo de apuração de imposto, ajustes podem ser necessários. Esses ajustes devem ser inseridos manualmente como adições e reduções.

Por fim, a apuração do imposto e os ajustes determinam o valor de CPRB que deve ser pago. No entanto, a geração do diário de pagamento e o registro nesse pagamento não são o escopo desse recurso.

Os períodos para esta avaliação de imposto devem ser gerenciados da mesma forma que outras avaliações de imposto. Em outras palavras, a apuração de imposto pode ser criada ou atualizada somente enquanto estiver aberta. Após ser finalizada, não poderá mais ser alterada a menos que seja reaberta.

Após a avaliação de imposto ser criada e quaisquer ajustes necessários sejam feitos, você pode gerar o evento periódico R-2060.

O evento R-2060 inclui os totais de avaliação de imposto e os detalhes dos cálculos de imposto por código de atividade econômico, ajustes e referências aos processos administrativos e judiciais.

### <a name="repro-step--setup"></a>Etapa de reprodução – Configuração

1. Acesse **Livros fiscais** \> **Configuração** \> **Organização fiscal**.
2. Defina a opção **CPRB** como **Sim** para habilitar a criação da apuração do INSS-CPRB e a transmissão do evento R-2060.
3. Acesse **Livros fiscais** \> **Configuração** \> **Sped Reinf** \> **Códigos de atividade econômica**. Os códigos de atividades econômicas devem ser configurados para habilitar o cálculo automático dos valores do imposto INSS-CPRB, pois a nota fiscal não possui informações relacionadas sobre esse imposto. Essa abordagem foi implementada para facilitar a configuração da matriz de impostos.
4. Selecione **Novo** para criar um código de atividade econômica e insira uma descrição. Consulte a Tabela 09 Sped REINF no site da autoridade fiscal.
5. Selecione o código de imposto que contém a alíquota de imposto para aplicar ao produto ou serviço. É necessário criar um tipo de imposto **INSS imposto**.
6. Na guia **Linha**, insira os produtos ou serviços que estão relacionados pela atividade econômica. Os produtos são identificados pelo código de classificação fiscal, e os serviços são identificados pelo código de serviço (federal).

### <a name="repro-step--create-a-tax-assessment-option-1"></a>Etapa Repro - Criar uma avaliação de imposto (opção 1)

1. Acesse **Livros fiscais** \> **Comum** \> **Período de reserva**.
2. Selecione um período de escrituração.
3. No Painel de Ação, selecione **INSS-CPRN** e, em seguida, selecione **Novo** para criar uma apuração de imposto. Uma avaliação de imposto para o período de reserva selecionado é criada automaticamente.

### <a name="repro-step--create-a-tax-assessment-option-2"></a>Etapa Repro - Criar uma avaliação de imposto (opção 2)

1. Acesse **Livros fiscais** \> **Comum** \> **Avaliação de imposto** \> **INSS-CPRB** e selecione **Avaliação de imposto INSS-CPRB**.
2. Selecione o período de escrituração e, em seguida, selecione **OK**.

> [!NOTE]
> Você poderá receber o seguinte aviso: “Linha XXXX: não foi possível identificar o código da atividade econômica”. Este aviso indica que o código de atividade econômica do documento fiscal relacionado e sua linha não foram encontrados. Neste caso, conclua a configuração que é descrita na etapa repro anterior.

**Excluir**

Você poderá excluir uma apuração do imposto INSS-CPRB existente se o status for **Aberto**.

**Documentos fiscais e operações não fiscais**

Quando os impostos INSS-CPRB são apurados, o valor tributável da nota fiscal é considerado e classificado durante o processo de apuração. Você pode visualizar as operações não fiscais e as notas fiscais relacionadas que fazem parte do cálculo do imposto.

**Transações de imposto**

Quando os impostos INSS-CPRB são apurados, você pode visualizar os detalhes das transações de imposto que são gerados pelo processo.

**Ajuste**

Você pode inserir transações de ajuste adicionais para ajustar (aumentar ou diminuir) o valor do INSS-CPRB calculado. Os códigos de ajuste podem ser configurados em **Livros fiscais** \> **Configuração** \> **Códigos de ajuste de imposto** \> **Tabela de códigos de ajustes INSS-CPRB**.

1. Selecione **Ajuste** para adicionar uma transação de ajuste que diminuirá ou aumentará o valor do imposto (débito) que é calculado.
2. Selecione o código de ajuste.
3. Insira uma descrição da transação relacionada.
4. Especifique o valor do ajuste e a atividade econômica.
5. Especifique a data do ajuste.

> [!NOTE]
> Os ajustes de INSS-CPRB estão disponíveis apenas por meio desse procedimento. O tipo de ajuste não está disponível em **Livros fiscais** \> **Diários** \> **Ajuste/benefício/incentivo geral do imposto**.

**Finalizar e reabrir**

Você pode finalizar ou reabrir a apuração do imposto INSS-CPRB relacionada.

Quando uma apuração do imposto INSS-CPRB é finalizada, nenhuma modificação é permitida nessa apuração para esse período, a menos que ela seja reaberta. Um comprovante é criado para postar o imposto INSS-CPRB a ser coletado, e as contas contábeis são definidas na postagem contábil para o imposto INSS em **Imposto** \> **Configuração** \> **Imposto de vendas** \> **Grupos de postagem contábil**.

> [!NOTE]
> Na atual arquitetura do SPED-Reinf definida pelo governo, o processo de pagamento e liquidação do passivo criado pela apuração de imposto será relatado a outro sistema chamado de DCTF Web. Este sistema consome a saída do SPED-Reinf e outros sistemas, tais como eSocial e PER/DCOMP. Entretanto, o processo de pagamento está atualmente fora do escopo e é fornecido por meio de outro recurso do Dynamics 365.

A ação **Reabrir** ficará disponível se o evento R-2060 já tiver sido fechado para o estabelecimento fiscal raiz e a avaliação de imposto já tiver finalizado. A ação **Reabrir** reverte o comprovante anterior que foi gerado pela ação de fechamento.

> [!NOTE]
> Siga as etapas descritas para o evento R-1000 a fim de inserir, atualizar ou cancelar o evento relacionado.

## <a name="events-r-2090--closing-and-r-2098--reopen"></a>Eventos R-2090 – Fechamento e R-2098 – Reabertura

**Fechamento**

Os eventos periódicos R-2010, R-2010 e R-2060 devem ser fechados ao final de um período, quando não houver mais nenhuma transação a ser relatada nesse período.

### <a name="repro-step"></a>Etapa de reprodução

1. Finalize a apuração do imposto INSS-CPRB, mesmo que você não apure o imposto INSS-CPRB.
2. Siga as etapas descritas para o evento R-1000 a fim de inserir, atualizar ou cancelar o evento relacionado.

**Reabrir**

Depois que os eventos periódicos R-2010, R-2010 e R-2060 forem fechados por meio de um evento R-2099, eles poderão ser reabertos por meio de um evento R-2098. Você poderá então relatar novas transações ou modificar transações existentes para o período.

### <a name="repro-step"></a>Etapa de reprodução

1. Reabra a apuração do imposto INSS-CPRB, mesmo que você não apure o imposto INSS-CPRB.
2. Siga as etapas descritas para o evento R-1000 a fim de inserir, atualizar ou cancelar o evento relacionado.

**Consultar evento 5011**

1. Quando o R-2090 for fornecido ao governo e seu status for atualizado para **Resposta pendente** (**Pendente resposta**), selecione **Executar processamento** e selecione **SPED Reinf**.
2. Defina o campo **Escolher** para **Habilitar**, selecione **Gerar** para gerar a mensagem XML e então **OK** para confirmar a ação.

    Depois que o item de mensagem é criado, o tipo de item de mensagem **Evento de fechamento** é atualizado e o status do item de mensagem é atualizado para **Consulta Gerada**.

3. Escolha **Executar processamento** e então **SPED Reinf**.
4. Defina o campo **Escolher ação** como **Habilitar** e selecione **Enviar consulta** para fornecer a consulta relacionada às autoridades fiscais.
5. Selecione **OK** para confirmar a ação. O tipo de item de mensagem **Evento de fechamento** é atualizado e o status do item de mensagem é atualizado para **Consulta Enviada**.
6. Escolha **Executar processamento** e então **SPED Reinf**.
7. Defina o campo **Escolher ação** como **Habilitar** e selecione **Obter resposta da consulta** para obter a aprovação da autoridade fiscal e o número de protocolo final, podendo assim fechar o período SPED-Reinf.
8. Selecione **OK** para confirmar a ação. O tipo de item de mensagem **Evento de fechamento** é atualizado e o status do item de mensagem é atualizado para **Aceito**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
