HiBCS
=====

#### �ر���ʾ��������������ٶ�Ӧ������(BAE)�еİٶ��ƴ洢(BCS)֧��

Licensed under the Apache License v2.0
--------------------------------------
http://www.apache.org/licenses/LICENSE-2.0

��װ
----

`config.php` ��дBAE���ݿ�����<br />
ͨ��ƽ̨�ṩ��phpMyAdmin����<br />
����`baefile.sql`��ʹ��`install.php`<br />
��֧��URL Rewrite�����н�`no-rewrite-index.php`������<br />
ֻ��`index.php`��дcss��ʽ��<br />
���ػ������ռ���ļ��ϴ����޸�`php.ini`��������:<br />

    post_max_size = 320M
    upload_max_filesize = 320M
    max_execution_time = 300
    max_input_time = 600
    memory_limit = 512M

#####��ӭ����ָ�� [Hi kooker](http://blog.kooker.jp/)

�ر�˵����
----------
ʹ�÷�BAE�����뽫`localhost-config.php`������Ϊ`config.php` �������ݿ⼰�ٶ��ƴ洢���
* 1���������޸�`config.php`�������
    * ���뽫 `$dbname` ��Ϊ������ݿ�����<br />
          ������β鿴�Լ������ݿ���������BAE��̨�������˵����л�����Ӧ��ҳ��鿴���ݿ����������ڵ�¼BAE��״̬��ֱ�Ӵ������ַ��http://developer.baidu.com/bae/bdbs/db
    * ������ `$ak` `$sk` ��д����ܳ׶ԡ����ڲ鿴�Լ����ܳ׶ԡ����û�����봴���������ڵ�¼BAE��״̬�´�
          http://developer.baidu.com/bae/ref/key
* 2������BAE��̨�ֶ�����һ��bucket<br />
        http://developer.baidu.com/bae/bcs/bucket ��ע�������޸�`config.php`���`$bucket`

����С��
--------
* 2012-11-24
    * �޸��ϴ����ݿ�СBUG
* 2012-11-28 
    * �����������⣬����del.php�����ļ��з��գ������ã���ʹ��ʱ������ȥ��`//require_once 'config.php';`ǰ��˫б��ע�ͣ�ʹ������ɾ�����ļ�<br />��ɾ�������ϴ���BCS���Ҽ�¼�����ݿ��object�����ļ���ɾ�����ݿ��¼�������force-install.php��װ���ݿ⣡��
    * config.php�����Լ�����URL
* 2012-12-6
    * ����install.php��װ�ļ�����װ����ɾ�����ļ�
    * ����force-install.php�����ļ��з��գ������ã���ǿ����װ�ļ����del.phpʹ�ã�����ɾ���ļ�����װ���ݣ�ʹ������ɾ�����ļ�
* 2012-12-12
    * ����del-list.php ����ɾ������ �����ļ��з��գ������ã�����ȫ�����������������
    * ����del-object.php ɾ���ļ��� �����ļ��з��գ������ã�����ȫ��������������������޸�del-list.php����Ӧ����
    * �������û�ϵͳ��������ֻ���Լ��õģ�û�Ǳ�Ҫ��

����
----
* nginx��URL Rewrite�����뽫���������뵽վ�������У�����nginx����

    `rewrite ^/page-([0-9]+)/?$ /index.php?page=$1 last;` <br />
    `rewrite ^/del-list-([0-9]+)$/?$ /del-list.php?page=$1 last; `

#### �����������������ظ��ϴ�ʱ�䣬��ֹ��ʱ��ˢ��`bcs.php`�ظ��ϴ������Դ����BUG����