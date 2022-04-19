# singers-and-their-partners-
Singers and their partners/cantantes y sus parejas
Queries para conocer las parejas y datos de determinados cantantes, combinando las tablas para lograr nuevas tablas que contengan la información que más nos interesa

Estas son las queries que realizamos:

SELECT a.fullname as singer, b.fullname as singer_partner FROM partners
JOIN singers a
ON partners.partner_1 = a.id
JOIN singers b
ON partners.partner_2 = b.id; 

SELECT singers.fullname as singer, songs.title as song FROM singers
JOIN songs
ON songs.id = singers.id;

SELECT a.fullname as singer, b.fullname as partner, songs.title as song FROM partners
JOIN singers a
ON partners.partner_1 = a.id
JOIN singers b
ON partners.partner_2 = b.id
JOIN songs
ON songs.id = a.id;    

SELECT COUNT (*) famous_condition,
CASE WHEN 
"famous_condition" = "Yes" THEN "Famous couple" WHEN "famous_condition" = "No" THEN "Not famous couple"
END as "couples fame condition" FROM partners GROUP BY "famous_condition";

SELECT singers.fullname, birthdate.DATE FROM singers 
JOIN birthdate
ON singers.id = birthdate.id;












