# Models
## User

<table style="width:100%" >
<tr><td colspan="2"><strong>User</strong></td></tr>
<tr><td>_id</td><td>ObjectId</td></tr>
<tr><td>displayName</td><td>String</td></tr>  
<tr><td>image</td><td>[Resource]</td></tr>
<tr><td>username</td><td>ObjectId</td></tr>  
<tr><td>role</td><td>admin/user</td></tr>  
</table> 

## AccessToken
<table>
<tr><td colspan="2"><strong>AccessToken</strong></td></tr>
<tr><td>accessToken</td><td>String</td></tr>
<tr><td>userId</td><td>objectId</td></tr>
<tr><td>email</td><td>String</td></tr> 
</table>

## Category
<table>
<tr><td colspan="2"><strong>Category</strong></td></tr>
<tr><td>_id</td><td>ObjectId</td></tr>
<tr><td>name</td><td>String</td></tr>
<tr><td>slug</td><td>String</td></tr>
<tr><td>parentCategory</td><td>Category</td></tr>
<tr><td>positionFromRoot</td><td>{ "x": int, "y": int }</td></tr>
<tr><td>courseTags</td><td>[Tag]</td></tr>
<tr><td>subCategories</td><td>[Category]</td></tr>
</table>
 
## Tag
<table>
<tr><td colspan="2"><strong>Tag</strong></td></tr>
<tr><td>_id</td><td>ObjectId</td></tr>
<tr><td>name</td><td>String</td></tr>
<tr><td>slug</td><td>String</td></tr> 
<tr><td>dateAdded</td><td>Date()</td></tr> 
</table>
 
## CoursePreview
<table>
<tr><td colspan="2"><strong>CoursePreview</strong></td></tr>
<tr><td>_id</td><td>ObjectId</td></tr>
<tr><td>name</td><td>String</td></tr>
<tr><td>slug</td><td>String</td></tr>
<tr><td>picture</td><td>String (URL)</td></tr>
<tr><td>video</td><td>String (URL)</td></tr>
<tr><td>dateAdded</td><td>Date()</td></tr>
<tr><td>createdBy</td><td>{"name": String}</td></tr>
</table>
 
## Course
<table>
<tr><td colspan="2"><strong>Course</strong></td></tr>
<tr><td>_id</td><td>ObjectId</td></tr>
<tr><td>name</td><td>String</td></tr>
<tr><td>slug</td><td>String</td></tr>
<tr><td>smallDescription</td><td>String</td></tr>
<tr><td>description</td><td>String</td></tr>
<tr><td>settings</td><td>Mixed</td></tr>
<tr><td>tabsActive</td><td>Mixed</td></tr>
<tr><td>category</td><td>Category</td></tr>
<tr><td>courseTags</td><td>[Tag]</td></tr>
<tr><td>picture</td><td>String (URL)</td></tr>
<tr><td>video</td><td>String (URL)</td></tr>
<tr><td>dateAdded</td><td>Date()</td></tr>
<tr><td>createdBy</td><td>{"name": String}</td></tr>
</table>

## Post Discussion
<table>
<tr><td colspan="2"><strong>Post</strong></td></tr>
<tr><td>_id</td><td>ObjectId</td></tr>
<tr><td>parentPost</td><td>postId</td></tr>  
<tr><td>content</td><td>String</td></tr>
<tr><td>courseId</td><td>ObjectId</td></tr> 
<tr><td>createdBy</td><td>User</td></tr>
<tr><td>dateAdded</td><td>Date()</td></tr> 
<tr><td>dateUpdated</td><td>Date()</td></tr> 
<tr><td>title</td><td>String</td></tr>
<tr><td>totalVotes</td><td>int</td></tr>
</table> 

## Link
<table>
<tr><td colspan="2"><strong>Link</strong></td></tr>
<tr><td>_id</td><td>ObjectId</td></tr>
<tr><td>content</td><td>String</td></tr>
<tr><td>contentNode</td><td>ObjectId</td></tr> 
<tr><td>createdBy</td><td>User</td></tr>
<tr><td>dateAdded</td><td>Date()</td></tr> 
<tr><td>dateUpdated</td><td>Date()</td></tr> 
<tr><td>title</td><td>String</td></tr>
<tr><td>totalVotes</td><td>int</td></tr>
</table> 

## TreeNode
<table>
<tr><td colspan="2"><strong>TreeNode</strong></td></tr>
<tr><td>_id</td><td>ObjectId</td></tr>
<tr><td>name</td><td>String</td></tr>  
<tr><td>Resources</td><td>[Resource]</td></tr>
<tr><td>courseId</td><td>ObjectId</td></tr> 
<tr><td>positionFromRoot</td><td>{ "y": int, "x": int }</td></tr>
<tr><td>isDeleted</td><td>boolean</td></tr>
<tr><td>dateAdded</td><td>Date()</td></tr>
<tr><td>createdBy</td><td>{"name": String}</td></tr> 
<tr><td>type</td><td>String (subTopic | contentNode)</td></tr>
<tr><td>childrens</td><td>[TreeNode]</td></tr>
</table>

## Resource
<table>
<tr><td colspan="2"><strong>Resource</strong></td></tr>
<tr><td>_id</td><td>ObjectId</td></tr>
<tr><td>courseId</td><td>ObjectId</td></tr> 
<tr><td>treeNodeId</td><td>ObjectId</td></tr> 
<tr><td>link</td><td>String (URL)</td></tr>
<tr><td>dateAdded</td><td>Date()</td></tr>
<tr><td>createdBy</td><td>{"name": String}</td></tr> 
<tr><td>type</td><td>String (pdf | video | youtube | mp4)</td></tr> 
</table>