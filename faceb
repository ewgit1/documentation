
When the user post then data will go into 2 tables .


create table vt_user_frs
(
usr_id     text,
fr_id  set<text>,
PRIMARY KEY (usr_id)
);
```
vt_user_frs



(select)
where we are using?

When a  user does a Post , then we will fetch all his friends from vt_user_frs.

For all these friends  we create an entry in vt_frs_posts.


INSERT


UPDATE


DELETE 


```




create table vt_my_posts
(
usr_id text,
pst_id uuid,
pst_dt timestamp,
PRIMARY KEY ((usr_id),pst_dt,pst_id)
) WITH CLUSTERING ORDER BY (pst_dt DESC,pst_id desc);

create table vt_frs_posts
(
usr_id text,
pst_id uuid,
pst_dt timestamp,
PRIMARY KEY ((usr_id),pst_dt,pst_id)
) WITH CLUSTERING ORDER BY (pst_dt DESC,pst_id desc);



create table vt_usr_posts
(
pst_id  uuid,
usr_id text,
pst_dt timestamp,
primary key((usr_id),pst_dt,pst_id)
) WITH CLUSTERING ORDER BY (pst_dt DESC,pst_id desc);

create table vt_posts
(
pst_id uuid ,
pst_dt timestamp,
pst_msg text,
pst_img set<text>,
pst_vid set<text>,
pst_crt_by text,
pst_date timestamp,
primary key((pst_id),pst_dt)
)  WITH CLUSTERING ORDER BY (pst_dt DESC);







