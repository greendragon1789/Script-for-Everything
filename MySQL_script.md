# Script using special case in MySQL database administration

### Script update for column with polygon type.
If don't using script it will appear GEOMETRY error.
```
SET @t = 'POLYGON((20.26864195432947 106.44781608562869,20.628158045670528 106.44781608562869,20.628158045670528 106.83148391437132,20.26864195432947 106.83148391437132,20.26864195432947 106.44781608562869))'
SET @g = GeomFromText(@t,0)
UPDATE tb_cities SET polygon_coordinates = @g where id=4
```
