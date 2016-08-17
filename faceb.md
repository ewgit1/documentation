
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


```
When user comes to his profile page

```

create table vt_frs_posts
(
usr_id text,
pst_id uuid,
pst_dt timestamp,
PRIMARY KEY ((usr_id),pst_dt,pst_id)
) WITH CLUSTERING ORDER BY (pst_dt DESC,pst_id desc);


```

When User comes to HomePage we show his friends and his posts as well



```



create table vt_posts
(
pst_id uuid ,
pst_dt timestamp,
pst_msg text,
pst_img set<text>,
pst_vid set<text>,
pst_crt_by text,
pst_date timestamp,
pst_feel text,
pst_tgt text,
pst_tag_frs SET<text>,
primary key((pst_id),pst_dt)
)  WITH CLUSTERING ORDER BY (pst_dt DESC);

```
This table holds the details of the User Posts.

```

create table w_usr_noti
(
usr_id text,
pst_id uuid,
pst_usr text,
pst_ts timestamp,
vw_flg boolean,
noti_txt text,
primary key((usr_id),vw_flg)
)



