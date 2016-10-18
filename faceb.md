
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
pst_mfy_date timestamp,
pst_feel text,
pst_tgt text,
pst_typ text,
pst_shr_txt text,
pst_tag_frs SET<text>,
pst_qry_id uuid,
pst_qry_desc text,
primary key(pst_id)
) ;

CREATE TABLE ew1.vt_posts_crt_by (
    pst_crt_by text,
    pst_tgt text,
    pst_id uuid,
    pst_dt timestamp,
    pst_feel text,
    pst_img set<text>,
    pst_mfy_date timestamp,
    pst_msg text,
    pst_tag_frs set<text>,
    pst_typ text,
    pst_shr_txt text,
    pst_vid set<text>,
    pst_qry_id uuid,
pst_qry_desc text,
    PRIMARY KEY ((pst_crt_by, pst_tgt), pst_id)
) WITH CLUSTERING ORDER BY (pst_id ASC)






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


create table ew_rec_frs
(
usr_id text,
fr_id text,
add_dt timestamp,
fr_req_snt text,
primary key((usr_id),fr_id)
);


insert into ew_rec_frs(usr_id,fr_id,add_dt,fr_req_snt) values('ew1','hr',toTimestamp(now()),'N');
insert into ew_rec_frs(usr_id,fr_id,add_dt,fr_req_snt) values('sarju','hr',toTimestamp(now()),'N');
insert into ew_rec_frs(usr_id,fr_id,add_dt,fr_req_snt) values('sarju','ew1',toTimestamp(now()),'N');
insert into ew_rec_frs(usr_id,fr_id,add_dt,fr_req_snt) values('hr','ew1',toTimestamp(now()),'N');

create table ew_fr_req_snt
(
usr_id text,
fr_id text,
req_dt timestamp,
req_sts text,
primary key((usr_id),fr_id)
);

create table ew_fr_req_rcvd
(
usr_id text,
fr_id text,
req_dt timestamp,
req_sts text,
primary key((fr_id),usr_id)
);


create table ew_frs
(
usr_id text,
fr_id text,
req_dt timestamp,
primary key((fr_id),usr_id)
);





create table ew_cb_my_flw
(
usr_id text,
flw_id set<text>,
flw_dt timestamp,
primary key(usr_id)
);

create table ew_cb_i_flw
(
usr_id text,
flw_id set<text>,
flw_dt timestamp,
primary key((fr_id),usr_id)
);




create table ew_pst_like_stats
(
pst_id uuid,
like_cnt counter,
love_cnt counter,
haha_cnt counter,
wow_cnt counter,
sad_cnt counter,
angry_cnt counter,
dlike_cnt counter,
primary key (pst_id)
);

create table ew_pst_like
(
pst_id uuid,
usr_id text,
like_typ  text,
crt_ts timestamp,
primary key(pst_id,usr_id)
);

create table ew_fr_req_noti
(
frm_usr_id text,
to_usr_id text,
noti_msg text,
noti_vw_flg text,
snt_ts  timestamp,
primary key((to_usr_id),frm_usr_id)
)




