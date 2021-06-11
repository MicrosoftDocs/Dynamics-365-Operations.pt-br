---
title: Pessoa
description: Este tópico descreve a entidade Pessoa para o Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 31a60dcf26d014e3588152254d84182218096172
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054587"
---
# <a name="person"></a>Pessoa

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve a entidade Pessoa para o Dynamics 365 Human Resources.

Nome físico: mshr_dirpersonentity

### <a name="description"></a>Descrição

Esta entidade fornece as informações pessoais para a pessoa que é o candidato.

## <a name="json-representation"></a>Representação JSON

```json
{
    "mshr_partynumber": "String",
    "mshr_name": "String",
    "mshr_namealias": "String",
    "mshr_knownas": "String",
    "mshr_languageid": "String",
    "mshr_addressbooks": "String",
    "mshr_anniversaryday": Int,
    "mshr_anniversarymonth": Int,
    "mshr_anniversaryyear": Int,
    "mshr_birthday": Int,
    "mshr_birthmonth": Int,
    "mshr_birthyear": Int,
    "mshr_childrennames": "String",
    "mshr_gender": Int,
    "mshr_hobbies": "String",
    "mshr_initials": "String",
    "mshr_maritalstatus": Int,
    "mshr_phoneticfirstname": "String",
    "mshr_phoneticlastname": "String",
    "mshr_phoneticmiddlename": "String",
    "mshr_personalsuffix": "String",
    "mshr_personaltitle": "String",
    "mshr_professionalsuffix": "String",
    "mshr_professionaltitle": "String",
    "mshr_fullprimaryaddress": "String",
    "mshr_addresscity": "String",
    "mshr_addresscountryregionid": "String",
    "mshr_addresscountryregionisocode": "String",
    "mshr_addresscounty": "String",
    "mshr_addressdistrictname": "String",
    "mshr_addresslatitude": Decimal,
    "mshr_addresslocationid": "000003212",
    "mshr_addresslocationroles": "Home",
    "mshr_addresslongitude": Decimal,
    "mshr_addressstate": "String",
    "mshr_addressstreet": "String",
    "mshr_addressvalidfrom": "Date",
    "mshr_addressvalidto": "Date",
    "mshr_addresszipcode": "String",
    "mshr_addressisprivate": Int,
    "mshr_addressdescription": "String",
    "mshr_primarycontactemail": "String",
    "mshr_primarycontactemaildescription": "String",
    "mshr_primarycontactemailisim": Int,
    "mshr_primarycontactemailpurpose": "String",
    "mshr_primarycontactfax": "String",
    "mshr_primarycontactfaxdescription": "String",
    "mshr_primarycontactfaxextension": "String",
    "mshr_primarycontactfaxpurpose": "String",
    "mshr_primarycontactphone": "String",
    "mshr_primarycontactphonedescription": "String",
    "mshr_primarycontactphoneextension": "String",
    "mshr_primarycontactphoneismobile": Int,
    "mshr_primarycontactphonepurpose": "String",
    "mshr_primarycontacttelex": "String",
    "mshr_primarycontacttelexdescription": "String",
    "mshr_primarycontacttelexpurpose": "String",
    "mshr_primarycontacturl": "String",
    "mshr_primarycontacturldescription": "String",
    "mshr_primarycontacturlpurpose": "String",
    "mshr_primarycontactfacebook": "String",
    "mshr_primarycontactfacebookdescription": "String",
    "mshr_primarycontactfacebookisprivate": Int,
    "mshr_primarycontactfacebookpurpose": "String",
    "mshr_primarycontactlinkedin": "String",
    "mshr_primarycontactlinkedindescription": "String",
    "mshr_primarycontactlinkedinisprivate": Int,
    "mshr_primarycontactlinkedinpurpose": "String",
    "mshr_primarycontacttwitter": "String",
    "mshr_primarycontacttwitterdescription": "String",
    "mshr_primarycontacttwitterisprivate": Int,
    "mshr_primarycontacttwitterpurpose": "String",
    "mshr_partytype": "String",
    "mshr_namesequencedisplayas": "String",
    "mshr_firstname": "String",
    "mshr_lastnameprefix": "String",
    "mshr_lastname": "String",
    "mshr_middlename": "String",
    "mshr_electroniclocationid": "String",
    "mshr_dirpersonentityid": "Guid",
    "mshr_addresstimezone": Int
}
```

## <a name="properties"></a>Propriedades

| Propriedade<br>**Nome físico**<br>**_Tipo_** | Usar | Descrição |
| --- | --- | --- |
| **ID da entidade Pessoa**<br>mshr_dirpersonentityid<br>*GUID* | Somente leitura<br>Obrigatório<br>Gerado pelo sistema | Um identificador exclusivo gerado pelo sistema para o registro de entidade. |
| **Número do participante**<br>mshr_partynumber<br>*Cadeia de caracteres* | Somente leitura<br>Obrigatório<br>Gerado pelo sistema | Um identificador único gerado pelo sistema, legível pelo usuário, para a pessoa.  |
| **Nome**<br>mshr_name<br>*Cadeia de caracteres* | Somente leitura<br>Obrigatório | O valor do campo é uma concatenação de Nome, Nome do Meio, Prefixo de Sobrenome e Sobrenome na ordem definida no campo **Sequência de Nome Exibida Como**. |
| **Alias de Nome**<br>mshr_namealias<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Um alias de nome que pode ser fornecido para a pessoa. |
| **Conhecido como**<br>mshr_knownas<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Um nome que pode ser usado para a pessoa se for normalmente conhecido como outro nome. |
| **ID do Idioma**<br>mshr_languageid<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | A ID de idioma do idioma principal da pessoa, conforme definido no formato ISO 639-1. |
| **Catálogos de endereços**<br>mshr_addressbooks<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Catálogo de endereços ao qual a pessoa pode ser atribuída. Os catálogos de endereços que foram configurados para a organização são listados na entidade mshr_diraddressbooksentity. |
| **Dia do aniversário**<br>mshr_anniversaryday<br>*Int* | Ler/gravar<br>Opcional | O dia da data de aniversário da pessoa. |
| **Mês do aniversário**<br>mshr_anniversarymonth<br>*conjunto de opções mshr_monthsofyear* | Ler/gravar<br>Opcional | O mês da data de aniversário da pessoa. |
| **Ano do aniversário**<br>mshr_anniversaryyear<br>*Int* | Ler/gravar<br>Opcional | O ano da data de aniversário da pessoa. |
| **Dia do nascimento**<br>mshr_birthday<br>*Int* | Ler/gravar<br>Opcional | O dia da data de nascimento da pessoa. |
| **Mês do nascimento**<br>mshr_birthmonth<br>*conjunto de opções mshr_monthsofyear* | Ler/gravar<br>Opcional | O mês da data de nascimento da pessoa. |
| **Ano de nascimento**<br>mshr_birthyear<br>*Int* | Ler/gravar<br>Opcional | O ano da data de nascimento da pessoa. |
| **Nomes de filhos**<br>mshr_childrennames<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Cadeia de caracteres dos nomes dos filhos da pessoa. Não há uma delimitação necessária. |
| **Sexo**<br>mshr_gender<br>*conjunto de opções mshr_hcmpersongender* | Ler/gravar<br>Opcional | O sexo da pessoa. |
| **Hobbies**<br>mshr_hobbies<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Os hobbies da pessoa. |
| **Iniciais**<br>mshr_initials<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | As iniciais do nome da pessoa. |
| **Estado Civil**<br>mshr_maritalstatus<br>*conjunto de opções mshr_hcmpersonmaritalstatus* | Ler/gravar<br>Opcional | O estado civil da pessoa. |
| **Nome fonético**<br>mshr_phoneticfirstname<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | A pronúncia fonética do nome da pessoa. |
| **Sobrenome fonético**<br>mshr_phoneticlastname<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | A pronúncia fonética do sobrenome da pessoa. |
| **Nome do meio fonético**<br>mshr_phoneticmiddlename<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | A pronúncia fonética do sobrenome da pessoa. |
| **Sufixo pessoal**<br>mshr_personalsuffix<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | O sufixo pessoal da pessoa. Os valores válidos na entidade mshr_dirnameaffixentity em que mshr_type é o sufixo (200000001). |
| **Título pessoal**<br>mshr_personaltitle<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Um título pessoal da pessoa. Os valores válidos na entidade mshr_dirnameaffixentity em que mshr_type é o título (200000000).
| **Sufixo do profissional**<br>mshr_professionalsuffix<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Sufixo de um profissional. |
| **Título profissional**<br>mshr_professionaltitle<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Título de um profissional. |
| **Endereço principal completo**<br>mshr_fullprimaryaddress<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | O endereço principal completo da pessoa, uma concatenação dos campos de endereço principal. |
| **Cidade do Endereço**<br>mshr_addresscity<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | A cidade do endereço principal da pessoa. Configurado na entidade mshr_logisticsaddresscityentity. |
| **País/região do endereço**<br>mshr_addresscountryregionid<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | O país/região do endereço principal da pessoa. Os valores válidos na entidade mshr_logisticsaddresscountryregionentity. |
| **Código ISO de país/região do endereço**<br>mshr_addresscountryregionisocode<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | O código ISO do país do endereço principal da pessoa. |
| **País do endereço**<br>mshr_addresscounty<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | A região do endereço principal da pessoa. Configurado na entidade mshr_logisticsaddresscountyentity. |
| **Nome do bairro do endereço**<br>mshr_addressdistrictname<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | O bairro do endereço principal da pessoa. Configurado na entidade mshr_logisticsaddressdistrictentity. |
| **Latitude do endereço**<br>mshr_addresslatitude<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | A latitude do endereço principal da pessoa. |
| **ID de local do endereço**<br>mshr_addresslocationid<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | O identificador exclusivo do local do endereço principal da pessoa. Os valores válidos na entidade mshr_logisticspostaladdresslocationcdsentity. |
| **Funções de Local do Endereço**<br>mshr_addresslocationroles<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | A função de local do endereço principal da pessoa. Configurado na entidade mshr_logisticslocationrolecdsentity. |
| **Longitude de endereço**<br>mshr_addresslongitude<br>*Cadeia de caracteres* |  Ler/gravar<br>Opcional | A longitude do endereço principal da pessoa. |
| **Estado do endereço**<br>mshr_addressstate<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | O estado do endereço principal da pessoa. Configurado na entidade mshr_logisticsaddressstateentity. |
| **Endereço**<br>mshr_addressstreet<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | O endereço principal da pessoa. |
| **Endereço válido a partir de**<br>mshr_addressvalidfrom<br>*Data* | Ler/gravar<br>Opcional | A data a partir da qual o endereço principal da pessoa é válido. |
| **Endereço válido até**<br>mshr_addressvalidto<br>*Data* | Ler/gravar<br>Opcional | A data até a qual o endereço principal da pessoa é válido. |
| **CEP do endereço**<br>mshr_addresszipcode<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | O código postal do endereço principal da pessoa. Configurado na entidade mshr_logisticsaddresspostalcodeentity. |
| **Endereço é particular**<br>mshr_addressisprivate<br>*conjunto de opções mshr_noyes* | Ler/gravar<br>Opcional | Determina se o endereço principal da pessoa é compartilhado com outras pessoas na organização. |
| **Descrição do Endereço**<br>mshr_addressdescription<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Descrição do endereço principal da pessoa. |
| **Email de Contato Principal**<br>mshr_primarycontactemail<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | O endereço de email principal da pessoa. |
| **Descrição de email do contato principal**<br>mshr_primarycontactemaildescription<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Uma descrição fornecida para o endereço de email principal. |
| **Email de contato principal é IM**<br>mshr_primarycontactemailisim<br>*conjunto de opções mshr_noyes* | Ler/gravar<br>Opcional | Determina se o endereço de email principal está disponível para mensagens instantâneas. |
| **Finalidade do email de contato principal**<br>mshr_primarycontactemailpurpose<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | A finalidade do endereço de email principal. Configurado na entidade mshr_logisticslocationroleentity. |
| **Fax de contato principal**<br>mshr_primarycontactfax<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Número de fax principal. |
| **Descrição de fax do contato principal**<br>mshr_primarycontactfaxdescription<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Descrição fornecida para o número de fax principal. |
| **Ramal do fax do contato principal**<br>mshr_primarycontactfaxextension<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | O ramal do número de fax principal. |
| **Finalidade do fax de contato principal**<br>mshr_primarycontactfaxpurpose<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | A finalidade do número de fax principal. Configurado na entidade mshr_logisticslocationroleentity.
| **Telefone do contato principal**<br>mshr_primarycontactphone<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Número de telefone principal. |
| **Descrição do telefone do contato principal**<br>mshr_primarycontactphonedescription<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Descrição fornecida para o número de telefone principal. |
| **Ramal do telefone do contato principal**<br>mshr_primarycontactphoneextension<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | O ramal do número de telefone principal. |
| **O telefone do contato principal é móvel**<br>mshr_primarycontactphoneismobile<br>*conjunto de opções mshr_noyes* | Ler/gravar<br>Opcional | Determina se o número de telefone principal é um telefone celular. |
| **Finalidade do telefone de contato principal**<br>mshr_primarycontactphonepurpose<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | A finalidade do número de telefone principal. Configurado na entidade mshr_logisticslocationroleentity. |
| **Telex do contato principal**<br>mshr_primarycontacttelex<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Número de telex principal. |
| **Descrição de telex do contato principal**<br>mshr_primarycontacttelexdescription<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Descrição fornecida para o número de telex principal da pessoa. |
| **Finalidade do telex de contato principal**<br>mshr_primarycontacttelexpurpose<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | A finalidade do número de telex principal da pessoa. Configurado na entidade mshr_logisticslocationroleentity. |
| **URL de contato principal**<br>mshr_primarycontacturl<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | A URL principal. |
| **Descrição de URL do contato principal**<br>mshr_primarycontacturldescription<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Descrição fornecida para a URL principal da pessoa. |
| **Finalidade da URL de contato principal**<br>mshr_primarycontacturldescription<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | A finalidade da URL principal da pessoa. Configurado na entidade mshr_logisticslocationroleentity. |
| **Contato principal do Facebook**<br>mshr_primarycontactfacebook<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Conta principal do Facebook. Identificado pela ID do usuário. |
| **Descrição de Facebook do contato principal**<br>mshr_primarycontactfacebookdescription<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Descrição fornecida para a conta principal de Facebook da pessoa. |
| **O contato principal do Facebook é particular**<br>mshr_primarycontactfacebookisprivate<br>*conjunto de opções mshr_noyes* | Ler/gravar<br>Opcional | Determina se a conta principal do Facebook é visível para outros usuários. |
| **Finalidade da contato principal do Facebook**<br>mshr_primarycontactfacebookpurpose<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | A finalidade da conta principal da pessoa no Facebook. Configurado na entidade mshr_logisticslocationroleentity. |
| **LinkedIn do contato principal**<br>mshr_primarycontactlinkedin<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Conta principal do LinkedIn. Identificado pelo nome do usuário. |
| **Descrição do contato principal do LinkedIn**<br>mshr_primarycontactlinkedindescription<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Descrição fornecida para a conta principal de LinkedIn da pessoa. |
| **O contato principal do LinkedIn é particular**<br>mshr_primarycontactlinkedinisprivate<br>*conjunto de opções mshr_noyes* | Ler/gravar<br>Opcional | Determina se as informações da conta principal do LinkedIn da pessoa são compartilhadas com outros usuários. |
| **Finalidade do LinkedIn do contato principal**<br>mshr_primarycontactlinkedinpurpose<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | A finalidade da conta principal da pessoa no LinkedIn. Configurado na entidade mshr_logisticslocationroleentity. |
| **Twitter do contato principal**<br>mshr_primarycontacttwitter<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | A conta principal do Twitter da pessoa. Identificado pelo @username. |
| **Descrição do Twitter do contato principal**<br>mshr_primarycontacttwitterdescription<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Descrição fornecida para a conta principal de Twitter da pessoa. |
| **O contato principal do Twitter é particular**<br>mshr_primarycontacttwitterisprivate<br>*conjunto de opções mshr_noyes* | Ler/gravar<br>Opcional | Determina se as informações da conta principal do Twitter da pessoa são compartilhadas com outros usuários. |
| **Finalidade do Twitter do contato principal**<br>mshr_primarycontacttwitterpurpose<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | A finalidade da conta principal da pessoa no Twitter. Configurado na entidade mshr_logisticslocationroleentity. |
| **Tipo de participante**<br>mshr_partytype<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | O tipo de participante da pessoa. Sempre será **Pessoa** para candidatos. |
| **Exibição da sequência de nomes como**<br>mshr_namesequencedisplayas<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | A sequência na qual as propriedades de nome da pessoa são concatenadas para formar o valor de propriedade do nome (mshr_name). |
| **Nome**<br>mshr_firstname<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório | O nome da pessoa. |
| **Nome do Meio**<br>mshr_middlename<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | O nome intermediário da pessoa. |
| **Prefixo do sobrenome**<br>mshr_lastnameprefix<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | O prefixo do sobrenome da pessoa. |
| **Sobrenome**<br>mshr_lastname<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | O sobrenome da pessoa. |
| **ID da localização eletrônica**<br>mshr_electroniclocationid<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | A ID da localização eletrônica da pessoa. |
| **Fuso horário do endereço**<br>mshr_addresstimezone<br>*Int* | Ler/gravar<br>Opcional | O fuso horário do endereço principal da pessoa. |

## <a name="see-also"></a>Consulte também

[Introdução da API de integração do sistema de acompanhamento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Exemplo de consulta de candidato a ser contratado](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]