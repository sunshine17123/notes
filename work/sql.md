=======================可用=======================
-- 通用：
 -- 展示最大链接数
show max_connections;
-- 
SELECT COUNT(*) from pg_stat_activity;
select min_val, max_val from pg_settings where name='max_connections';

SELECT datname, count(*) FROM pg_stat_activity GROUP BY datname;


-- 自增起始数设置成1
select setval('data_board_id_seq',1);
-- 把当前最大的id做为当前的id自增起始数
select setval('your_table_id_seq',(select max(id) from 表名));

select setval('triggerwords_id_seq',(select max(id) from triggerwords));


-- 清空所有表数据并将索引置1  
TRUNCATE TABLE success_data RESTART IDENTITY CASCADE;
