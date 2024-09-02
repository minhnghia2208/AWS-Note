# Object Strorage (Amazon S3)
- Object storage stores data data as an object (image, file, document, ...)
and it's associated metadata
- Object storage stores data in flat namespace (no hierachy). 
- Objects are identified by their harsh ID

# Block Storage (AWS EBS)
- Block Storage breaks data into fixed-size blocks (from KB to MB) that can be read or written individually
- Each blocks is assigned with unique address and block number for lookup
- Block strorage allows read and write on a specific block without changing the whole dataset that the block belongs to
- For AWS, EBS can only be attached to one EC2, except Provisioned IPOS

# File Storage (AWS EFS)
- File Storage uses files and folders to organize data
- Similar to Files and Folders system
- For AWS, EFS can be shared among EC2s

### Reference: 
- https://cloud.google.com/discover/object-vs-block-vs-file-storage
- https://aws.amazon.com/compare/the-difference-between-block-file-object-storage/