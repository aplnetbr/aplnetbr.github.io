select      a.cd_estabelecimento cd,
            A.NM_FANTASIA_ESTAB || ' (' || a.cd_estabelecimento || ')' ds
from        tasy.estabelecimento a,
            tasy.pessoa_juridica b
where       a.cd_cgc = b.cd_cgc
--and         a.ie_situacao = 'A'
order by 2 asc;

select      a.cd_estabelecimento cd,
            A.NM_FANTASIA_ESTAB ds
from        tasy.estabelecimento a,
            tasy.pessoa_juridica b
where       a.cd_cgc = b.cd_cgc
and         a.ie_situacao = 'A'
--and         a.cd_estabelecimento -- 82 IRA, 83 IRA BH, 97 MICROIMAGEM
and         upper(a.nm_fantasia_estab) like '%MICRO%' 
order by 2 asc;

-- Utilizado para Filtrar somente os estabelecimentos OCPM no Parâmetro SQL do relatorio
--WHERE       A.CD_ESTABELECIMENTO = NVL(:CD_ESTAB,A.CD_ESTABELECIMENTO)
--AND         A.CD_ESTABELECIMENTO IN (67,74,82,83,97)


SELECT      A.CD_ESTABELECIMENTO CD,
            A.NM_FANTASIA_ESTAB DS
FROM        TASY.ESTABELECIMENTO A,
            TASY.PESSOA_JURIDICA B
WHERE       A.CD_CGC = B.CD_CGC
AND         A.IE_SITUACAO = 'A'
--AND         A.CD_ESTABELECIMENTO
ORDER BY 2 ASC;

-------------------------------------------------------------------------------


select      a.cd_estabelecimento cd,
            A.NM_FANTASIA_ESTAB || ' (' || a.cd_estabelecimento || ')' ds
from        tasy.estabelecimento a,
            tasy.pessoa_juridica b
where       a.cd_cgc = b.cd_cgc
and         a.ie_situacao = 'A'
and         a.CD_ESTABELECIMENTO IN (28,31,34,4,36)
order by 2;


-------------------------------------------------------------------------------


SELECT  A.CD_EMPRESA CD,
        A.NM_RAZAO_SOCIAL DS
FROM    TASY.EMPRESA A
WHERE   A.CD_EMPRESA = :CD_EMPRESA_COR
ORDER BY DS ASC;


------------------------------------------------------------------------------

SELECT  obter_endereco_pessoa_juridica(A.CD_CGC) ENDERECO
FROM    ESTABELECIMENTO A
WHERE   A.CD_ESTABELECIMENTO = :CD_ESTABELECIMENTO_COR;

-------------------------------------------------------------------------------

SELECT  Obter_municipio_pj(A.CD_ESTABELECIMENTO) CIDADE,
        A.NM_FANTASIA_ESTAB ESTAB
FROM    ESTABELECIMENTO A
WHERE   A.CD_ESTABELECIMENTO = :CD_ESTABELECIMENTO_COR;

-----------------------------------------------------------------------------------------------------------------

select Obter_municipio_pj(A.CD_ESTABELECIMENTO) ||', '|| to_char(sysdate,'DD "de" Month "de" YYYY') CIDADE_DATA
FROM    ESTABELECIMENTO A
WHERE   A.CD_ESTABELECIMENTO = :CD_ESTABELECIMENTO_COR;

select      a.cd_estabelecimento cd,
            A.NM_FANTASIA_ESTAB ds
from        tasy.estabelecimento a,
            tasy.pessoa_juridica b
where       a.cd_cgc = b.cd_cgc
and         a.ie_situacao = 'A'
and         a.cd_estabelecimento = :cd_estab
order by 2 asc


select cd_estabelecimento cd,
       nm_fantasia_estab ds
  from tasy.estabelecimento       
 where ie_situacao = 'A'
order by 2

select  a.cd_estabelecimento cd,
           a.nm_fantasia_estab ds
from    estabelecimento a
where a.ie_situacao = 'A'
order by ds

-- CONDICAO PARA TRAZER SOMENTE OS ESTABELECIMENTOS OCPM --
/*
WHERE       A.CD_ESTABELECIMENTO = NVL(DECODE(:CD_ESTAB,0,A.CD_ESTABELECIMENTO,:CD_ESTAB),A.CD_ESTABELECIMENTO)
AND         A.CD_ESTABELECIMENTO IN (19,34,67,74,82,83,90,97)
*/


-- FILTRO PARA PARAMETRO --
/*
SELECT      A.CD_ESTABELECIMENTO CD,
            A.NM_FANTASIA_ESTAB DS
FROM        TASY.ESTABELECIMENTO A,
            TASY.PESSOA_JURIDICA B
WHERE       A.CD_CGC = B.CD_CGC
AND         A.IE_SITUACAO = 'A'
AND         A.CD_ESTABELECIMENTO IN (67,74,82,83,90,97)
ORDER BY 2 ASC
*/

-- CONDICAO PARA TRAZER TODOS OS ESTABELECIMENTOS OU SOMENTE O SELECIONADO



