---
title: Configurar a integração fiscal para canais do Commerce
description: Este tópico fornece diretrizes para configurar a funcionalidade de integração fiscal para canais do Commerce.
author: josaw
ms.date: 02/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: epopov
ms.search.validFrom: 2018-11-1
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: bc87972b1cd2e04d31a3d48132cd1de42353698d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801908"
---
# <a name="set-up-the-fiscal-integration-for-commerce-channels"></a>Configurar a integração fiscal para canais do Commerce

[!include [banner](../includes/banner.md)]

## <a name="introduction"></a>Apresentação

Este tópico fornece diretrizes para configurar a funcionalidade de integração fiscal para canais do Commerce. Para obter mais informações sobre a integração fiscal, consulte [Visão geral da integração fiscal dos canais do Commerce](fiscal-integration-for-retail-channel.md).

O processo de configuração da integração fiscal inclui as seguintes tarefas:

1. Configure conectores fiscais que representam dispositivos ou serviços fiscais usados para fins de registro fiscal, como impressoras fiscais.
2. Configure provedores de documentos que geram documentos fiscais que serão registrados em dispositivos ou serviços fiscais por conectores fiscais.
3. Configure o processo de registro fiscal que define uma sequência de etapas de registro fiscal e os conectores fiscais e provedores de documentos fiscais usados para cada etapa.
4. Atribua o processo de registro fiscal a perfis de funcionalidade de ponto de venda (PDV).
5. Atribua perfis técnicos de conectores a perfis de hardware.

## <a name="set-up-a-fiscal-registration-process"></a>Configurar um processo de registro fiscal

Antes de usar a funcionalidade de integração fiscal, você deve definir as configurações a seguir.

1. Atualizar parâmetros do Commerce.

    1. Na página **Parâmetros compartilhados do Commerce**, na guia **Geral**, defina a opção **Habilitar integração fiscal** como **Sim**. Na guia **Sequências numéricas**, defina as sequências numéricas para as seguintes referências:

        - Número do perfil técnico fiscal
        - Número do grupo do conector fiscal
        - Número do processo de registro

    2. Na página **Parâmetros do Commerce**, defina a sequência numérica para o número do perfil funcional fiscal.

    > [!NOTE]
    > Sequências numéricas são opcionais. Os números de todas as entidades de integração fiscal podem ser gerados a partir de sequências numéricas ou manualmente.

2. Carregue configurações de conectores fiscais e provedores de documentos fiscais.

    Um provedor de documentos fiscais é responsável por gerar documentos fiscais que representam transações e eventos registrados no PDV em um formato que também é usado para a interação com um dispositivo ou serviço fiscal. Por exemplo, um provedor de documentos fiscais pode gerar uma representação de um recibo fiscal em um formato XML.

    Um conector fiscal é responsável pela comunicação com um dispositivo ou serviço fiscal. Por exemplo, um conector fiscal pode enviar um recibo fiscal que um provedor de documentos fiscais criou em um formato XML para uma impressora fiscal. Para obter mais detalhes sobre componentes de integração fiscal, consulte [Processo de registro fiscal e exemplos de integração fiscal para dispositivos fiscais](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices).

    1. Na página **Conectores fiscais** (**Retail e Commerce \> Configuração de canal \> Integração fiscal \> Conectores fiscais**), carregue uma configuração XML para cada dispositivo ou serviço que você planeja usar para fins de integração fiscal.

        > [!TIP]
        > Selecionando **Exibir**, é possível exibir todos os perfis funcionais e técnicos relacionados ao conector fiscal atual.

    2. Na página **Provedores de documentos fiscais** (**Retail e Commerce \> Configuração de canal \> Integração fiscal \> Provedores de documentos fiscais**), carregue uma configuração XML para cada dispositivo ou serviço que você planeja usar.

        > [!TIP]
        > Selecionando **Exibir**, é possível exibir todos os perfis funcionais relacionados ao provedor de documentos fiscais atual.

    Para obter exemplos de configurações de conectores fiscais e provedores de documentos fiscais, consulte [Exemplos de integração fiscal no SDK do Retail](fiscal-integration-for-retail-channel.md#fiscal-integration-samples-in-the-retail-sdk).

    > [!NOTE]
    > O mapeamento de dados é considerado uma parte do provedor de documentos fiscais. Para configurar diferentes mapeamentos de dados para o mesmo conector (por exemplo, regulamentações específicas de estado), crie diferentes provedores de documentos fiscais.

3. Crie perfis funcionais de conectores e perfis técnicos de conectores.

    1. Na página **Perfis funcionais do conector** (**Retail e Commerce \> Configuração de canal \> Integração fiscal \> Perfis funcionais do conector**), crie um perfil funcional de conector para cada combinação de um conector fiscal e um provedor de documentos fiscais relacionado a esse conector fiscal.

        1. Selecione um nome de conector.
        2. Selecione um provedor de documento.

        É possível alterar os parâmetros de mapeamento de dados em um perfil funcional do conector. Para restaurar os parâmetros padrão definidos na configuração do provedor de documentos fiscais, selecione **Atualizar**.

        **Exemplos**

        |   | Formatar | Exemplo |
        |---|--------|---------|
        | **Configurações de alíquotas de IVA** | valor: VATrate | 1 : 2000, 2 : 1800 |
        | **Mapeamento dos códigos IVA** | VATcode : valor | vat20 : 1, vat18 : 2 |
        | **Mapeamento de tipos de meio de pagamento** | TenderType : valor | Caixa: 1, cartão: 2 |

        > [!NOTE]
        > Os perfis funcionais do conector são específicos da empresa. Se você planeja usar a mesma combinação de um conector fiscal e um provedor de documentos fiscais em empresas diferentes, crie um perfil funcional de conector para cada empresa.

    2. Na página **Perfis técnicos do conector** (**Retail e Commerce \> Configuração de canal \> Integração fiscal \> Perfis técnicos do conector**), crie um perfil técnico de conector para cada conector fiscal.

        1. Selecione um nome de conector.
        2. Selecione um tipo de conector. Para dispositivos conectados a uma estação de hardware, selecione **Local**.

            > [!NOTE]
            > Atualmente, somente conectores locais são compatíveis.

        Parâmetros nas guias **Dispositivo** e **Configurações** em um perfil técnico do conector podem ser alterados. Para restaurar os parâmetros padrão definidos na configuração do conector fiscal, selecione **Atualizar**. Enquanto uma nova versão de uma configuração XML é carregada, você recebe uma mensagem informando que o conector fiscal atual ou o provedor de documentos fiscais já está sendo usado. Esse procedimento não substitui alterações manuais que foram feitas anteriormente em perfis funcionais de conectores e perfis técnicos de conectores. Para aplicar o conjunto padrão de parâmetros de uma nova configuração, na página **Perfis funcionais do conector** ou na página **Perfis técnicos do conector**, selecione **Atualizar**.

4. Crie grupos de conectores fiscais.

    Um grupo de conectores fiscais combina perfis funcionais de conectores fiscais que executam funções idênticas e são usados na mesma etapa de um processo de registro fiscal. Por exemplo, se vários modelos de impressoras fiscais puderem ser usados em uma loja, os conectores fiscais dessas impressoras fiscais poderão ser combinados em um grupo de conectores fiscais.

    1. Na página **Grupo do conector fiscal** (**Retail e Commerce \> Configuração de canal \> Integração fiscal \> Grupos do conector fiscal**), crie um grupo de conectores fiscais.
    2. Adicione perfis funcionais ao grupo de conectores. Na guia **Perfis funcionais**, selecione **Adicionar** e selecione um número do perfil. Cada conector fiscal em um grupo de conectores pode ter apenas um perfil funcional.
    3. Para suspender o uso do perfil funcional, defina a opção **Desabilitar** como **Sim**. Essa alteração só afeta o grupo de conectores atual. Você pode continuar usando o mesmo perfil funcional em outros grupos de conectores.

5. Crie um processo de registro fiscal.

    Um processo de registro fiscal é definido pela sequência de etapas de registro e pelo grupo de conectores usado para cada etapa.

    1. Na página **Processo de registro fiscal** (**Retail e Commerce \> Configuração de canal \> Integração fiscal \> Processos de registros fiscais**), crie um registro para cada processo exclusivo de registro fiscal.
    2. Adicione as etapas do registro ao processo:

        1. Selecione **Adicionar**.
        2. Selecione um tipo de conector fiscal.
        3. No campo **Número do grupo**, selecione um grupo de conectores fiscais apropriado.

6. Atribua entidades do processo de registro fiscal a perfis de PDV.

    1. Na página **Perfis de funcionalidade de PDV** (**Retail e Commerce \> Configuração de canal \> Configuração do PDV \> Perfis de PDV \> Perfis de funcionalidade**), atribua o processo de registro fiscal a um perfil de funcionalidade de PDV. Selecione **Editar** e, na guia **Processo de registro fiscal**, no campo **Número do processo**, selecione um processo.
    2. Na página **Perfil de hardware do PDV** (**Retail e Commerce \> Configuração de canal \> Configuração do PDV \> Perfis de PDV \> Perfis de hardware**), atribua perfis técnicos do conector a um perfil de hardware. Selecione **Editar**, adicione uma linha na guia **Periféricos fiscais** e, no campo **Número do perfil**, selecione um perfil técnico do conector.

    > [!NOTE]
    > Você pode adicionar vários perfis técnicos ao mesmo perfil de hardware. No entanto, um perfil de hardware ou um perfil de funcionalidade de PDV deve ter apenas uma interseção com qualquer grupo de conectores fiscais.

    O fluxo de registro fiscal é definido pelo processo de registro fiscal e também por alguns parâmetros de componentes de integração fiscal: a extensão de tempo de execução do Commerce para o provedor de documentos fiscais e a extensão da estação de hardware para o conector fiscal.

    - A inscrição de eventos e transações no registro fiscal é predefinida no provedor de documentos fiscais.
    - O provedor de documentos fiscais também é responsável por identificar o conector fiscal usado para o registro fiscal. Ele corresponde aos perfis funcionais do conector que estão incluídos no grupo de conectores fiscais especificado para a etapa atual do processo de registro fiscal com o perfil técnico do conector que é atribuído ao perfil de hardware da estação de hardware ao qual o PDV está emparelhado.
    - O provedor de documentos fiscais usa as configurações de mapeamento de dados da configuração do provedor de documento fiscal para transformar dados de transação/evento, como impostos e pagamentos, enquanto um documento fiscal é gerado.
    - Quando o provedor de documentos fiscais gera um documento fiscal, o conector fiscal pode enviá-lo para o dispositivo fiscal como está ou analisá-lo e transformá-lo em uma sequência de comandos da interface de programação de aplicativo (API) do dispositivo, dependendo de como a comunicação é tratada.

7. Na página **Processo de registro fiscal** (**Retail e Commerce \> Configuração de canal \> Integração fiscal \> Processos de registros fiscais**), selecione **Validar** para validar o processo de registro fiscal.

    Recomendamos que você execute esse tipo de validação nos seguintes casos:

    - Depois de concluir todas as configurações de um novo processo de registro, inclusive quando você atribui processos de registro a perfis de funcionalidade de PDV e perfis de hardware.
    - Depois de fazer alterações em um processo de registro fiscal existente, essas alterações podem fazer com que um conector fiscal diferente seja selecionado no tempo de execução (por exemplo, se você alterar o grupo de conectores para uma etapa do processo de registro fiscal, habilite um perfil funcional de conector em um grupo de conectores ou adicione um novo perfil funcional do conector a um grupo de conectores).
    - Depois de fazer alterações na atribuição de perfis técnicos de conectores a perfis de hardware.

8. Na página **Agenda de distribuição**, execute os trabalhos **1070** e **1090** para transferir dados para o banco de dados do canal.

## <a name="set-up-fiscal-texts-for-discounts"></a>Configurar textos fiscais para descontos

Em alguns casos, um texto especial deve ser impresso em um recibo fiscal se um desconto for aplicado. Você pode configurar textos fiscais para descontos na página **Grupo do conector fiscal** (**Retail e Commerce \> Configuração de canal \> Integração fiscal \> Grupos do conector fiscal**).

- Para descontos manuais aplicados no PDV, defina um texto fiscal para o código de informação ou o grupo de códigos de informação especificado como o código de informação do **Desconto de produto** no perfil de funcionalidade do PDV.

    1. Na página **Grupo do conector fiscal**, selecione **Texto do recibo fiscal**.
    2. Na guia **Códigos de informação**, selecione **Adicionar** e selecione um código de informação ou um grupo de códigos de informação.
    3. No **Número do código de informação**, selecione um valor.
    4. No campo **Número de subcódigo**, selecione um valor se for necessário um subcódigo para o código de informação selecionado.
    5. No campo **Texto do recibo fiscal**, especifique um texto fiscal que deve ser impresso em um recibo fiscal.
    6. Defina a opção **Imprimir entrada de usuário no recibo fiscal** como **Sim** para substituir o texto em um recibo fiscal com informações que um usuário insere manualmente no PDV. Essa opção aplica-se apenas aos códigos de informação que possuem um tipo de entrada de **Texto**.

    > [!NOTE]
    > Você pode especificar um texto fiscal para vários códigos de informação para dar suporte a cenários em que grupos de códigos de informação, códigos de informação vinculados e códigos de informação acionados são usados. Nesses cenários, o recibo fiscal conterá os textos fiscais de todos os códigos de informação vinculados à linha de transação na qual o desconto foi aplicado.

- Para descontos específicos do canal, você deve definir um texto fiscal para o código de desconto.

    1. Na página **Grupo do conector fiscal**, selecione **Texto do recibo fiscal**.
    2. Na guia **Descontos**, selecione **Adicionar** e selecione uma ID do desconto.
    3. No campo **Texto do recibo fiscal**, especifique um texto fiscal que deve ser impresso em um recibo fiscal.

    > [!NOTE]
    > Se vários descontos forem aplicados à mesma linha de transação, o recibo fiscal conterá textos fiscais de todos os descontos vinculados a essa linha de transação.

## <a name="set-error-handling-settings"></a>Definir configurações de tratamento de erros

As opções de tratamento de erros disponíveis na integração fiscal são definidas no processo de registro fiscal. Para obter mais informações sobre o tratamento de erros na integração fiscal, consulte [Tratamento de erro](fiscal-integration-for-retail-channel.md#error-handling).

1. Na página **Processo de registro fiscal** (**Retail e Commerce \> Configuração de canal \> Integração fiscal \> Processos de registros fiscais**), você pode definir os parâmetros a seguir para cada etapa do processo de registro fiscal:

    - **Permitir ignorar** – Este parâmetro habilita a opção **Ignorar** na caixa de diálogo de tratamento de erros.
    - **Permitir marcar como registrado** – Este parâmetro habilita a opção **Marcar como registrado** na caixa de diálogo de tratamento de erros.
    - **Continuar se houver erro** – Se este parâmetro estiver habilitado, o processo de registro fiscal poderá continuar no terminal de PDV em caso de falha no registro de uma transação ou de um evento. Do contrário, para executar o registro fiscal da próxima transação ou evento, o operador deve repetir o registro fiscal com falha, ignorá-lo ou marcar a transação ou ao evento como registrados. Para obter mais informações, consulte [Registro fiscal opcional](fiscal-integration-for-retail-channel.md#optional-fiscal-registration).

    > [!NOTE]
    > Se o parâmetro **Continuar se houver erro** for habilitado, os parâmetros **Permitir ignorar** e **Permitir marcar como registrado** serão desabilitados automaticamente.

2. As opções **Ignorar** e **Marcar como registrado** na caixa de diálogo de tratamento de erros exigem a permissão **Permitir ignorar o registro ou marcar como registrado**. Por isso, na página **Grupos de permissões** (**Retail e Commerce \> Funcionários \> Grupos de permissões**), habilite a permissão **Permitir ignorar o registro ou marcar como registrado**.
3. As opções **Ignorar** e **Marcar como registrado** permitem que os operadores insiram informações adicionais quando o registro fiscal falha. Para disponibilizar essa funcionalidade, você deve especificar os códigos de informações **Ignorar** e **Marcar como registrado** em um grupo de conectores fiscais. As informações inseridas pelos operadores são salvas como uma transação de código de informação vinculada à transação fiscal. Para obter mais detalhes sobre códigos de informação, consulte [Códigos informativos e grupos de códigos informativos](../info-codes-retail.md).

    > [!NOTE]
    > A função do disparador **Produto** não é compatível com os códigos de informação que são usados para **Ignorar** e **Marcar como registrado** em grupos de conectores fiscais.

    - Na página **Grupo do conector fiscal**, na guia **Códigos de informação**, selecione códigos de informação ou grupos de códigos de informação nos campos **Ignorar** e **Marcar como registrado**.

    > [!NOTE]
    > Um documento fiscal e um documento não fiscal podem ser gerados em qualquer etapa de um processo de registro fiscal. Uma extensão de provedor de documentos fiscais identifica cada tipo de transação ou evento como relacionado a documentos fiscais ou não fiscais. O recurso de tratamento de erros aplica-se apenas a documentos fiscais.
    >
    > - **Nota fiscal** – Um documento obrigatório que deve ser registrado com sucesso (por exemplo, um recibo fiscal).
    > - **Documento não fiscal** – Um documento suplementar para a transação ou evento (por exemplo, um comprovante de cartão de presente).

4. Se o operador deve poder continuar a processar a operação atual (por exemplo, criar ou finalizar uma transação) após um erro de verificação de integridade, você deve habilitar a permissão **Permitir ignorar o erro de verificação de integridade** na página **Grupos de permissões** (**Retail e Commerce \> Funcionários \> Grupos de permissões**). Para obter mais informações sobre o procedimento de verificação de integridade, consulte [Verificação de integridade do registro fiscal](fiscal-integration-for-retail-channel.md#fiscal-registration-health-check).

## <a name="set-up-fiscal-xz-reports-from-the-pos"></a>Configurar relatórios fiscais X/Z a partir do PDV

Para permitir que os relatórios fiscais X/Z sejam executados a partir do PDV, você deve adicionar novos botões a um layout de PDV.

- Na página **Grades de botões**, siga as instruções em [Adicionar operações de PDV a layouts de PDV usando um Designer de grade de botões](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters) para instalar o designer e atualizar um layout de PDV.

    1. Selecione o layout para atualizar. 
    2. Adicione um novo botão e defina a propriedade do botão **Leitura X**.
    3. Adicione um novo botão e defina a propriedade do botão **Redução Z**.
    4. Na página **Agenda de distribuição**, execute o trabalho **1090** para transferir as alterações para o banco de dados do canal.

## <a name="enable-manual-execution-of-postponed-fiscal-registration"></a>Habilitar a execução manual do registro fiscal adiado

Para habilitar a execução manual de um registro fiscal adiado, você deve adicionar um novo botão a um layout do PDV.

- Na página **Grades de botões**, siga as instruções em [Adicionar operações de PDV a layouts de PDV usando um Designer de grade de botões](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters) para instalar o designer e atualizar um layout de PDV.

    1. Selecione o layout para atualizar.
    2. Adicione um novo botão e defina a propriedade do botão **Concluir processo de registro fiscal**.
    3. Na página **Agenda de distribuição**, execute o trabalho **1090** para transferir suas alterações para o banco de dados do canal.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]