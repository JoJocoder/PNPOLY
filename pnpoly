#This is a python version of Point Inclusion in Polygon Test comes from W. Randolph Franklin (WRF)  https://wrf.ecse.rpi.edu//Research/Short_Notes/pnpoly.html
#2017-12-25 
class Point(object):
	def __init__(self,p):
		self.p=p
	def __str__(self):
		return self.p
	def InPolygon(self,polygon,BoundCheck=False):
		inside=False
		if BoundCheck:
			minX=polygon[0][0]
			maxX=polygon[0][0]
			minY=polygon[0][1]
			maxY=polygon[0][1]
			for p in polygon:
				minX=min(p[0],minX)
				maxX=max(p[0],maxX)
				minY=min(p[1],minY)
				maxY=max(p[1],maxY)
			if self.p[0]<minX or self.p[0]>maxX or self.p[1]<minY or self.p[1]>maxY:
				return False
		j=len(polygon)-1
		for i in range(len(polygon)):
			if ((polygon[i][1]>self.p[1])!=(polygon[j][1]>self.p[1]) and (self.p[0]<(polygon[j][0]-polygon[i][0])*(self.p[1]-polygon[i][1])/( polygon[j][1] - polygon[i][1] ) + polygon[i][0])):
				inside =not inside
			j=i
		return inside
	
# In the case that most of the points you are checking are inside the bounding box, you could leave the bounding box check out.
#Example: 

# point=Point((3,1))
# polygonVerts=[(0,0),(0,1),(1,2),(2,1),(2,0)]
# isInside=point.InPolygon(polygonVerts,True)
# print(isInside)
