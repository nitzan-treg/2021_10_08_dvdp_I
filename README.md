#  Davidope I
This project is very much inspired by davidope's art https://www.instagram.com/dvdp/

It is an expiriment on stacking animation of rotation matrices together. It turned out to be more interesting then expected

```c++
// get required attributes
vector pos = v@P;
vector origin_offset = getbbox_center(1);
vector rot_axis = {0,1,0};

//find distance to pivot
float dist = distance(pos,origin_offset);
float falloff = fit(dist,chf('min_dist'),chf('max_dist'),0,1);
f@falloff = falloff;
falloff = chramp('falloff_remap',falloff);

//create a rotation matrix by the falloff
matrix rot = ident();
float rot_amp = falloff*chf('rotation_amp');
rotate(rot,rot_amp,rot_axis);

//rotate position using the rotation matrix
pos-=origin_offset;
pos*=rot;
pos+=origin_offset;

v@P = pos;

```


<img alt = "gif" src="Images/2021_10_08_dvdp_I.gif">
<img src="Images/Node Tree.png">

