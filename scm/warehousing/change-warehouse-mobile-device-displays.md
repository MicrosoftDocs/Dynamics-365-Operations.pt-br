---
title: "Configurações de exibição de dispositivo móvel de depósito"
description: "Este artigo descreve como configurar a aparência de uma exibição do dispositivo móvel e como controlar teclas de atalho do teclado, como botões."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SysUserSetup, WHSRFColor, WHSRFColorPicker, WHSWorkUserDisplaySettings
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 29071
ms.assetid: 931a02e8-b561-45e3-9c44-06b875ced1b4
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: afa59439e06aad9d669eb352a9837a013f447249
ms.openlocfilehash: 721b293d1f8c76458ca510732f9bb94f003ac6e3
ms.lasthandoff: 03/31/2017


---

# <a name="warehouse-mobile-device-display-settings"></a>Configurações de exibição de dispositivo móvel de depósito

Este artigo descreve como configurar a aparência de uma exibição do dispositivo móvel e como controlar teclas de atalho do teclado, como botões. 

Este artigo se aplica aos recursos de "depósito avançado" em Gerenciamento de depósito. Os dispositivos móveis podem ser usados para muitas tarefas executadas por trabalhadores de depósito.

## <a name="specify-styles-and-map-keyboard-shortcuts"></a>Especificar estilos e mapear atalhos de teclado
Como parte da configuração do dispositivo móvel, você pode definir layouts diferentes para dispositivos móveis. Para fazer isso, é necessário saber os nomes dos arquivos CSS (Folhas de Estilos em Cascata) e ASPX (Extensão Active Server Page). Os arquivos padrão são instalados como parte da instalação do Portal de Dispositivos Móveis de Depósito. Se não souber os nomes de arquivos, pergunte ao administrador do sistema. Você pode definir um novo estilo na página **Configurações de exibição do dispositivo móvel**:

-    No campo **Arquivo CSS**, insira o nome do arquivo CSS. Inclua a extensão de nome de arquivo .css.
-   No campo **Exibição das configurações de exibição do dispositivo móvel**, especifique o arquivo ASPX. **Não** inclua a extensão de nome de arquivo .aspx.

Os arquivos CSS e ASPX devem estar localizados em um diretório específico; assim, o aplicativo IIS (Serviços de Informações da Internet) pode carregá-los. Talvez seja útil definir arquivos CSS diferentes se você estiver executando a funcionalidade do dispositivo móvel em diferentes navegadores ou em tipos diferentes de hardware que exijam um outro controle de layout. As configurações simples como a cor do plano de fundo, a fonte e o tamanho da fonte do texto, e a largura e o comportamento de botões, podem ser facilmente controlados com o uso diferente de arquivos CSS. O arquivo ASPX é usado para exibir o site móvel do aplicativo ASP.NET do servidor. O arquivo controla como a estrutura geral do HTML é apresentada. É recomendável personalizar essa funcionalidade somente se você tiver problemas sérios estruturais com o HTML e o JavaScript. Este código deve ser alterado para os dispositivos específicos. Para mapear os controles HTML na página do dispositivo móvel para os atalhos de teclado, na página **Configurações de exibição do dispositivo móvel**, no campo **Atalho de teclado**, atribua os códigos numéricos para as teclas. Você pode usar o menu **Exibir códigos para atalhos de teclado** no dispositivo móvel para localizar os códigos de caracteres numéricos. Observe que os mapeamentos podem variar, dependendo do hardware empregado. Você deve usar a seguinte sintaxe para criar o mapeamento:

&lt;controle o código&gt;de =key&lt;de nome&gt;(nome&lt;da chave)&gt;;

Esta é uma explicação das partes da sintaxe:

-   **&lt;nome de controle&gt;** – o nome do controle (por exemplo, um botão) que são processados em HTML.
-   ** (&lt;nome&gt;da chave) ** – o nome da chave do teclado que você está criando para o atalho.
-   **&lt;Código principal&gt;** – o código de característica numérico da chave como usar a tecla de atalho.

Este é um exemplo:

Cancel(Esc)=27; Full(F2)=113

Em todas as páginas que incluam um botão **Cancelar**, o botão terá este texto:

**(Esc) Cancelar**

Se você pressionar a tecla Esc do teclado, ativará o botão **Cancelar**. Para aplicar as configurações do estilo e de atalho de teclado a um dispositivo específico, você deve criar um mapeamento no campo **Critérios**. Use uma expressão regular .NET para criar o mapeamento. A expressão deve consistir em três seções que são separadas por uma barra vertical (|), conforme mostrado aqui:

Endereço&lt;do host de Request.UserHostAddress=user&gt;_=_Nome&lt;do host de HostName=user&gt;_=_Exemplo&lt;de Request.UserAgent=user&gt;

Esta é uma explicação das partes da expressão:

-   **&lt;endereço do host ** de usuário&gt;– uma expressão regular do .NET que corresponda o endereço IP de usuários.
-   **&lt;nome do host ** de usuário&gt;– uma expressão regular do .NET que corresponda o nome da rede de usuários.
-   **&lt;user&gt;agent ** – uma expressão regular do .NET que corresponda o identificador do navegador que o usuário usa.

Este exemplo habilita o uso do Internet Explorer 8:

Request.UserHostAddress=.\*_=_HostName=.\*_=_Request.UserAgent=MSIE\\s8\\.0

Você pode usar o menu **Exibir configuração de servidor para configurações de exibição** no dispositivo móvel para encontrar informações sobre a configuração.

## <a name="define-text-colors-for-messages"></a>Definir cores de texto para mensagens
Você pode usar a página **Cores do texto do dispositivo móvel** para controlar as várias cores que são usadas em mensagens geradas pelo sistema, como mensagens de erro. Por exemplo, a cor de texto pode indicar a finalidade ou a gravidade da mensagem. Os seguintes tipos de mensagens são mostrados:

| Tipo de mensagem | Descrição                                                                                                                                                                            |
|--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Padrão      | As mensagens padrão usam as configurações de cor padrão para todas as mensagens, conforme definido pelo arquivo CSS para o Portal de Dispositivos Móveis de Depósito.                                                   |
| Erro        | As mensagens de erro indicam um problema que o usuário deve resolver antes de continuar.                                                                                             |
| Êxito      | As mensagens de êxito confirmam uma ação bem-sucedida.                                                                                                                                |
| Aviso      | As mensagens de aviso informam ao trabalhador que há um problema, ou que poderá existir um problema se o trabalhador continuar Mas, o trabalhador não precisa solucionar o problema para continuar. |

Para selecionar a cor, na página **Selecionar cor**, clique na paleta ou digite um código de cor hexadecimal.

## <a name="define-the-date-format-to-use-on-mobile-devices"></a>Definir o formato de data a ser usado em dispositivos móveis
Você pode estender a lista de formatos de data aceitos para cada instalação. Esta capacidade pode ser útil, por exemplo, se você deseja fornecer um formato que facilite a inserção por um trabalhador de datas em um dispositivo móvel. O formato padrão é determinado pelo idioma padrão do usuário, que é especificado no campo **Idioma** na página **Opções do usuário**. (A mesma página também é usado para associar um funcionário a um usuário específico de depósito). ** observação: ** Dispositivos móveis de depósito da configuração não usarem ** data e hora e formato numérico ** de campo ** preferências de idioma e de região ** na página. Para alterar um formato de data, você deve estar familiarizado com as expressões regulares no Microsoft .NET Framework. Para obter mais informações, consulte [Expressões regulares do .NET Framework](http://go.microsoft.com/fwlink/?LinkId=391260). Para definir formatos de data, edite o arquivo de Dates.ini que está localizado em configurações de conteúdo Dates.ini\\\\em servidor de portal de dispositivos móveis de depósito. Esse arquivo usa expressões regulares do .NET para especificar o formato de data. A expressão regular deve conter subexpressões que criam grupos nomeados para dia, mês e ano (DDMMAA), conforme mostrado no seguinte exemplo:

^ (?&lt;dia&gt;do\\) {2} (?&lt;mês&gt;do\\) {2} (?&lt;ano&gt;do\\) {2} $

Cada subexpressão requer um a dois dígitos para dia e mês, e um a quatro dígitos para o ano. Por exemplo, a seguinte subexpressão define um grupo nomeado para um ano, e requer no mínimo dois ou no máximo quatro dígitos:

(?&lt;ano&gt;\\de {2,4})

Você pode especificar mais de uma expressão no mesmo arquivo. Cada expressão deve estar em uma linha separada. A primeira expressão correspondente é usada para analisar a data.

<a name="see-also"></a>Consulte também
--------

[Configuration of mobile devices for warehouse work](configure-mobile-devices-warehouse.md)


