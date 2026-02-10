ALTER TABLE departments MODIFY department_id INT unsigned AUTO_INCREMENT PRIMARY KEY;

CREATE TABLE departments(
department_id int unsigned AUTO_INCREMENT PRIMARY KEY,
name VARCHAR(20) NOT NULL,
created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP on update CURRENT_TIMESTAMP
);

Q2
ALTER TABLE people ADD department_id INT unsigned after email;

Q3
INSERT INTO departments (name)
VALUES
('営業'),
('開発'),
('経理'),
('人事'),
('情報システム');

INSERT INTO people (name,email,department_id,age,gender)
VALUES
('桐生戦兎','kamenriderbuild@gizumo.jp','2','26','1'),
('万丈龍我','kamenridercross-z@gizumo.jp','1','23','1'),
('猿渡一海','kamenridergrease@gizumo.jp','1','29','1'),
('氷室幻徳','kamenriderrogue@gizumo.jp','3','35','1'),
('石動美空','mi-tan@gizumo.jp','5','19','2'),
('井上生真','kamenridergavv@gizumo.jp','1','19','1'),
('甘根幸果','hapipare@gizumo.jp','4','21','2'),
('飛電或人','kammenriderzero-one@gizumo.jp','2','22','1'),
('檀黎斗','kamenridergenmu@gizumo.jp','2','30','1'),
('酢賀研造','kamenriderbake@gizumo.jp','2','37','1');

INSERT INTO reports (person_id,content)
VALUES
('7','物理学者で研究と発明が趣味です。'),
('8','筋肉とプロテインが恋人です。'),
('9','仲間と一緒に畑仕事をしていてジャガイモが有名です。'),
('10','父親が知事をしており秘書として支えています。'),
('11','表の顔は品性構成表の顔は品行方正な優等生、裏の顔はネット配信でアイドル活動中'),
('12','お菓子が大好きで新しいお菓子に出会うと必ずノートに記録しています。'),
('13','独立して何でも屋として自営業しています。'),
('14','叔父から会社の社長に任命され、優秀な秘書に支えてもっています。'),
('15','ゲームを開発するのが好きで寝る時以外はゲームの開発に時間を使っています。'),
('16','研究が大好きで四六時中研究のことしか考えてません。');


Q4
UPDATE people SET department_id = '3' WHERE person_id = ;

Q5
select * from people WHERE gender = 1 order by age desc;

select name,age from people WHERE gender = 1 order by age desc;

Q6
SELECT
  `name`, `email`, `age`
FROM
  `people`
WHERE
  `department_id` = 1
ORDER BY
  `created_at`;

ピープルテーブル　名前とメールアドレスと年齢　営業のみ　コンテンツ作成昇順
＝peopleテーブル内で営業カラムの名前、email、年齢レコードのみ選択しcreated_atの昇順で並べて表示する。

Q7
❌select name,age from people WHERE age BETWEEN 20 and 29 and gender = 2; 
❌select name , age from people WHERE age BETWEEN 20 and 29 and gender = 2 or BETWEEN 40 and 49 and gender = 1;
select name , age from people 
WHERE 
(age BETWEEN 20 and 29 and gender = '2') 
or 
(age BETWEEN 40 and 49 and gender = '1');

Q8
select name,department_id,age  
from people 
WHERE department_id = 1
order by age ASC;

Q9
select AVG(age) average_age
from people
WHERE gender=2
group by department_id=2;

Q10
❌select
  name,content
　from
  people
　inner join
  reports
　on
  people.person_id=reports.person_id
　inner join
  departments
　on 
 people.department_id = departments.department_id;

⚪️
select
  people.name,reports.content,departments.name
from
  people
inner join
  reports
on
  people.person_id=reports.person_id
inner join
  departments
on 
 people.department_id = departments.department_id;

短縮版
select
  p.name,r.content,d.name
from
  people AS p
inner join
  reports AS r
on
  p.person_id=r.person_id
inner join
  departments AS d
on 
 p.department_id = d.department_id;

 Q11
⚪️
select
 people.name,reports.content
from
 people
inner join
 reports
on
 people.person_id = reports.person_id;

⚪️
select
 people.name,reports.content
from
 people
inner join
 reports
on
 people.person_id = reports.person_id
WHERE
 reports.content = '';

⚪️
select
 people.name,reports.content
from
 people
left join
 reports
on
 people.person_id = reports.person_id
 WHERE
 reports.content is NULL;
