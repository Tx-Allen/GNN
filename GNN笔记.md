## GNN的作用
<img width="853" alt="image" src="https://github.com/user-attachments/assets/3f37818b-0b02-4a29-84c4-3bdf76b1f62d">

- XA和XB之间可能有相关性，如果没有考虑X之间连接性的话，预测的结果可能不会那么准确
- GNN通过X的特征和X之间的连接性，预测Y（Node Label），一整张Graph的Label

## GNN包含的内容
<img width="963" alt="image" src="https://github.com/user-attachments/assets/c5f62c5e-0a15-43be-9ff0-c44f2dfc441f">

- Node：顶点
- Edge：边
- Node Feature：顶点的特征（可能不止一个特征）
- Edge Feature：边的特征（可能不止一个特征）
- Label or Value：想要预测的值

<img width="1041" alt="image" src="https://github.com/user-attachments/assets/99b0df14-78ca-4044-9857-7f9e3725da48">

- x：每个顶点的Feature（Node Feature），每个数组表示对应顶点的Feature，【点的数量，特征的数量】
- edge_index：点数量*2，表示两个点之间的边，1-0，0-1表示双向，【2（边的两个端点），边的数量】
  - e.g. 8个edge，edge是有方向性
- edge_attr：每个边上的feature，【边的数量，特征的数量】
- y：【边的数量，输出的维度】

<img width="903" alt="image" src="https://github.com/user-attachments/assets/c8b431fc-0953-440e-a850-d846c7e6a351">

## Message Passing
<img width="620" alt="image" src="https://github.com/user-attachments/assets/57026594-7bbd-46dd-96b5-806423034032">
<img width="684" alt="image" src="https://github.com/user-attachments/assets/51fe9d5b-f6fe-4f71-97ee-b30bc5789d5a">
<img width="725" alt="image" src="https://github.com/user-attachments/assets/c51f68bd-eded-4543-85d3-fe4fc004cf0e">

- <sup>0</sup>：表示第0个阶段
- <sub>0,1</sub>：表示第1个node传给第0个
- aggr(max, add, mean)：整合message的三种主要方式，取最大/相加/中位数，三选一

<img width="752" alt="image" src="https://github.com/user-attachments/assets/6597553b-4036-4de8-b101-a8b4ad68343c">

## Message Passing Class
<img width="639" alt="image" src="https://github.com/user-attachments/assets/723fd4be-a053-4414-a025-560ce280ec25">
<img width="775" alt="image" src="https://github.com/user-attachments/assets/782401c2-3f29-4114-a52e-c39b91a5a29f">

- self.aggr=定义用max/add/mean
- forward：message和update结合
- message：x_i本体，x_j邻居
- update：一倍的自己和aggr_out就是aggr后的message
- message passing深度取决于应用

<img width="733" alt="image" src="https://github.com/user-attachments/assets/84f33be7-eb54-47d4-ad46-db5afd911734">
<img width="719" alt="image" src="https://github.com/user-attachments/assets/64b94fd1-1325-4519-b065-146028c894f2">
<img width="726" alt="image" src="https://github.com/user-attachments/assets/50c2c7a1-686e-4913-89ac-3c0ac06bed3d">
<img width="724" alt="image" src="https://github.com/user-attachments/assets/a470d0aa-17bf-485d-937f-2d2459b1346e">
<img width="734" alt="image" src="https://github.com/user-attachments/assets/570c1e1f-3a57-4445-88f1-3d0153a676aa">
<img width="729" alt="image" src="https://github.com/user-attachments/assets/319a553e-c675-466f-87ac-04dbdeddd80c">
<img width="723" alt="image" src="https://github.com/user-attachments/assets/3b8290b1-d898-49de-95ff-d5c5dbd90d8e">

## Message Passing Mechanism
<img width="852" alt="image" src="https://github.com/user-attachments/assets/293e67b7-a857-4512-afc6-ba6c7c8aa5df">
<img width="1034" alt="image" src="https://github.com/user-attachments/assets/7e567323-6543-4474-84fb-dccce6f6a751">


## GNN Model
<img width="977" alt="image" src="https://github.com/user-attachments/assets/e48f8d92-389b-4807-beaf-0e7d3ee27ab2">
